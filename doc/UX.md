[Voltar para o índice](SPEC.md)



---

# UI/UX Multiplataforma (PC, Celular, Tablet)

O jogo precisa ser totalmente jogável em três classes de tela: **PC** (navegador, tela grande, mouse/teclado), **celular** (APK offline ou navegador, tela pequena, toque) e **tablet** (tela intermediária, toque, eventualmente com teclado/mouse acoplado). Não existe uma versão "principal" e outras "adaptadas": a interface deve ser pensada como responsiva desde o início, com os mesmos sistemas e a mesma profundidade de informação disponíveis em qualquer tamanho de tela, apenas reorganizados.

Ainda que este documento não especifique telas em detalhe de código, os seguintes princípios de UI/UX devem guiar a experiência em qualquer plataforma:

- **Painel central de "estado atual"**: sempre visível ou a um toque de distância, resumindo tempo atual (data simulada), energia/saúde/estresse/satisfação, situação profissional atual (cargo/empresa ou status de estudo/freelance/startup) e patrimônio.
- **Tela de alocação de tempo**: interface simples para distribuir horas disponíveis da semana entre as categorias de atividade (Seção 2.2), com feedback imediato de impacto estimado.
- **Feed de eventos**: lista cronológica de eventos recentes (oportunidades, crises, marcos, notificações de NPCs), com ações rápidas quando aplicável (aceitar/recusar proposta, responder convite).
- **Linha do tempo navegável**: visualização histórica completa da trajetória do jogador, filtrável por categoria (carreira, projetos, relacionamentos, achievements).
- **Perfil de personagem**: telas dedicadas para inspecionar em profundidade cada sistema (árvore de habilidades, reputação multidimensional, rede de relacionamentos, portfólio de projetos, finanças).
- **Avanço de tempo como ação central e recorrente**: botão/gesto proeminente para "avançar" o tempo (dia/semana/mês), sempre com resumo pós-avanço do que mudou.
- **Tela de slots de save**: tela dedicada, acessível a qualquer momento a partir do menu principal, mostrando os 3 slots de save manual. Cada slot exibe, quando ocupado, um resumo da partida (nome do personagem, tempo simulado, situação atual) e três ações: **carregar**, **salvar/sobrescrever** e **excluir** (com confirmação explícita para sobrescrever ou excluir). Slots vazios oferecem apenas a ação de iniciar/salvar uma nova partida ali. O estado do autosave em andamento é indicado separadamente dos 3 slots (ver `architecture/PERSISTENCE.md`), com opção de promovê-lo a um dos slots manuais.
- **Design responsivo por padrão, não "mobile-first" excludente**: componentes pensados para funcionar tanto por toque (celular/tablet) quanto por mouse/teclado (PC), com layout que se reorganiza por tamanho de tela (colunas/painéis extras em telas grandes, navegação por abas/gestos em telas pequenas) sem esconder ou simplificar informação nas telas menores; uso extensivo de resumos expansíveis (ex.: cartões que expandem para detalhe) para lidar bem tanto com telas pequenas quanto grandes.
- **Offline-first por design**: nenhuma funcionalidade essencial deve depender de conectividade, especialmente na versão APK (que deve ser 100% jogável sem rede). A versão web pode oferecer recursos adicionais quando online (ex.: sincronização), mas o loop principal de jogo funciona igual online ou offline; indicadores de save/autosave devem ser discretos mas confiáveis em qualquer plataforma.
- **Acessibilidade e clareza**: uso consistente de cores/ícones para status positivo/neutro/negativo em todas as métricas (saúde, estresse, finanças), evitando ambiguidade visual em decisões importantes, em qualquer tamanho de tela.

---