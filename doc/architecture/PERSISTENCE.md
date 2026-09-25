[Voltar para o índice](../SPEC.md)



---

# Persistência

O jogo é multiplataforma (PC, celular e tablet), distribuído em duas formas: **versão web** (jogável via navegador) e **versão mobile empacotada como APK**. O APK precisa rodar **completamente offline**, sem depender de servidor. A versão web pode ou não depender de backend, mas o estado de uma partida nunca pode ficar preso a um servidor específico: o modelo de dados e as regras desta seção são as mesmas em ambas as plataformas, mudando apenas o motor de armazenamento local usado por trás dos mesmos ports/interfaces de persistência definidos no domínio.

## Estratégia por plataforma

- **APK (mobile offline):** todo o estado (`SaveGame` e coleções associadas) é persistido em um banco/armazenamento local embarcado no próprio dispositivo (ex.: SQLite ou storage de arquivo local), sem chamadas de rede necessárias para jogar. Nenhuma funcionalidade essencial de jogo pode depender de conectividade.
- **Web (navegador):** o estado pode ser persistido localmente no navegador (ex.: IndexedDB/armazenamento local do navegador) para jogar sem backend, e/ou sincronizado com um backend (Spring Boot + PostgreSQL, a stack de referência para desenvolvimento/servidor) quando disponível. A experiência de jogo não deve travar se a rede cair; o autosave local do navegador deve continuar funcionando.
- **PC:** tratado como a mesma versão web/APK rodando em tela maior (ver `UX.md` para a estratégia responsiva). Não há motor de persistência específico para PC além dos dois acima.
- **Modelo de dados único:** independentemente do motor físico (PostgreSQL, SQLite, storage do navegador), o formato lógico do `SaveGame` e as regras de migração/validação descritas abaixo são as mesmas em todas as plataformas, garantindo que um save exportado em uma plataforma possa, em princípio, ser importado em outra (ver Export/Import).

## Save/Load

- Cada partida corresponde a um `SaveGame`, agregado raiz único contendo (ou referenciando) todo o estado necessário para reconstrução completa: Player, GameClock, e todas as coleções de entidades associadas.
- Suporte a **múltiplos saves** (múltiplas partidas independentes) por instalação, organizados em **slots fixos** (3 slots de save manual por instalação/perfil).
- Cada slot pode estar **vazio** ou **ocupado** por um `SaveGame`. A tela de slots (ver `UX.md`) mostra, para cada slot ocupado, um resumo do estado da partida (nome do personagem, tempo simulado atual, cargo/situação atual) para o jogador identificar qual save é qual antes de carregar.
- O jogador pode, a qualquer momento, a partir da tela de slots: **salvar** no slot escolhido (sobrescrevendo o que houver nele, com confirmação explícita se o slot já estiver ocupado), **carregar** um slot ocupado, ou **excluir** o save de um slot (com confirmação explícita, já que é uma ação destrutiva e não coberta por autosave/backup do próprio slot excluído).
- **Autosave é independente dos 3 slots manuais**: existe sempre um save automático da partida em andamento (ver seção Autosave abaixo), que não ocupa nenhum dos 3 slots manuais, mas pode ser promovido a um slot manual quando o jogador escolhe salvar.
- Load reconstrói o estado completo e valida integridade antes de disponibilizar a partida para interação.

## Autosave

- Autosave disparado por: intervalos de tempo real (ex.: a cada N minutos de sessão ativa), marcos de avanço de tempo simulado (ex.: ao final de cada mês/ano simulado), e antes de qualquer operação de risco (ex.: decisão irreversível como pedir demissão, encerrar startup).
- Autosave não deve bloquear a interação do jogador (execução assíncrona/reativa), com indicação não intrusiva de status (salvando/salvo/falha).
- Configurável pelo jogador (frequência, ativar/desativar, mantendo ao menos um autosave mínimo de segurança sempre ativo).

## Backup

- Geração periódica de backups completos do save (cópias íntegras, não incrementais, para simplicidade e robustez), com política de retenção configurável (ex.: manter últimos N backups automáticos).
- Backups armazenados localmente, em local distinto do save ativo, para proteger contra corrupção do arquivo/registro principal.

## Export/Import

- Export gera um arquivo portátil (formato serializado versionado, ex. JSON estruturado ou binário compacto) representando o `SaveGame` completo, permitindo transferência entre dispositivos ou compartilhamento/arquivamento manual pelo jogador.
- Import valida o arquivo (assinatura de versão, integridade estrutural, compatibilidade) antes de substituir ou adicionar como novo save.

## Versionamento e Migração de Saves

- Todo `SaveGame` carrega um número de versão de esquema.
- Mudanças no modelo de domínio ao longo do desenvolvimento exigem **rotinas de migração** explícitas (transformação de save de versão N para N+1), mantidas e testadas como parte do próprio sistema (nunca descartando saves antigos silenciosamente).
- Migrações devem ser **encadeáveis** (um save muito antigo passa por múltiplas migrações sequenciais até a versão atual) e idempotentes quando possível.

## Validação e Recuperação

- Toda operação de load/import executa validação estrutural (referências íntegras entre entidades, valores dentro de faixas plausíveis, ausência de ciclos inválidos) antes de aceitar o save como válido.
- Em caso de corrupção detectada, o sistema deve tentar recuperação automática a partir do backup válido mais recente, informando claramente o jogador sobre o que ocorreu (e o quanto de progresso, se algum, foi potencialmente perdido).
- Falhas de validação não recuperáveis nunca devem travar a aplicação; devem ser reportadas de forma clara, preservando o arquivo corrompido para eventual diagnóstico manual, em vez de sobrescrevê-lo.

---