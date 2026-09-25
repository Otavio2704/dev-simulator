# SPEC — Dev Simulator

Jogo multiplataforma (PC, celular e tablet) de simulação de vida e carreira de um desenvolvedor de software ao longo de décadas, distribuído como versão web (navegador) e versão mobile empacotada em APK que roda completamente offline. Este é o ponto de entrada da documentação do projeto. As seções abaixo foram organizadas em arquivos separados para facilitar leitura, manutenção e uso como contexto por fases de desenvolvimento.

## 1. Visão e Princípios do Jogo

Dev Simulator é um jogo multiplataforma (PC, celular e tablet) de simulação de vida e carreira, distribuído como versão web e como APK mobile offline, no qual o jogador cria e conduz a trajetória de um desenvolvedor de software ao longo de anos e décadas. O jogo não tem enredo linear, não tem final fixo e não define um caminho "certo". Cada partida é uma história diferente, resultado das escolhas do jogador, do acaso controlado pela geração procedural e da evolução independente do mundo simulado.

> **Nota de escopo (atualização posterior ao documento original):** o SPEC original definia o jogo como "mobile offline". O escopo foi expandido para multiplataforma (PC, celular, tablet), mantendo a obrigatoriedade de funcionamento 100% offline na versão empacotada em APK. Todas as regras de sistemas, progressão e domínio permanecem inalteradas; o que muda é a estratégia de distribuição/persistência (ver `architecture/ARCHITECTURE.md` e `architecture/PERSISTENCE.md`) e a abordagem de UI/UX (ver `UX.md`), agora responsiva para qualquer tamanho de tela.

### Princípios fundamentais

- **Sem MVP e sem caminho obrigatório.** O jogo não guia o jogador para uma sequência única de decisões. Cada sistema (carreira, conhecimento, projetos, reputação, vida pessoal) evolui de forma paralela e o jogador escolhe onde investir tempo.
- **Múltiplas vitórias, nenhuma vitória.** Não existe "fim de jogo" com condição de vitória única. O jogador define seus próprios objetivos: riqueza, impacto técnico, reconhecimento acadêmico, liderança, legado em Open Source, equilíbrio de vida, ou qualquer combinação.
- **Consequência real e persistente.** Toda decisão deixa marcas duradouras. Um projeto abandonado, uma entrevista mal feita, uma amizade cultivada por anos, todos esses eventos ficam registrados e influenciam o que acontece depois.
- **Tempo é o recurso mais escasso.** O jogador nunca tem tempo suficiente para fazer tudo. Especializar-se em uma área custa não fazer outra coisa. Isso cria trade-offs reais entre curto e longo prazo.
- **O jogo não exige grind constante.** O jogador pode "avançar o tempo" sem realizar ações manuais em toda unidade de tempo. Atividades de longo prazo (cursos, projetos, tratamentos de saúde) continuam progredindo enquanto o tempo passa, mesmo sem interação constante.
- **Mundo vivo.** NPCs, empresas, tecnologias e o mercado de trabalho evoluem de forma independente da linha do jogador. Uma tecnologia pode nascer, crescer, dominar o mercado e depois declinar. Empresas nascem, crescem, são compradas ou falem. NPCs têm suas próprias carreiras, que se cruzam com a do jogador.
- **Simulação profunda, não arcade.** Números, curvas de progresso, deterioração de habilidades por desuso, curvas de mercado e economia devem parecer plausíveis e ter causa e efeito rastreáveis, mesmo que simplificados frente à realidade.
- **Data-driven por padrão.** Qualquer conteúdo que possa ser expresso como dado (tecnologia, cargo, empresa, evento, achievement, NPC arquetípico) deve ser definido em configuração externa, não em código, permitindo expansão contínua sem alterar o núcleo do domínio.

---

---

## 2. Loop Principal

O loop principal do Dev Simulator opera em múltiplas escalas de tempo simultâneas, permitindo que o jogador atue em detalhe no curto prazo e delegue o médio/longo prazo ao sistema de simulação.

### 2.1. Escalas de tempo

- **Dia:** unidade mínima de simulação. Ações pontuais (estudar um tópico específico, participar de uma reunião, responder uma entrevista) consomem uma fração do dia (manhã, tarde, noite) ou o dia inteiro.
- **Semana:** unidade usada para consolidar rotina (horas de trabalho, horas de estudo, horas de projeto pessoal, horas de lazer/descanso).
- **Mês:** unidade usada para eventos de médio prazo (pagamento de salário, cobrança de despesas fixas, avaliação de desempenho no emprego, avanço de disciplinas em cursos).
- **Ano:** unidade usada para marcos de carreira, formaturas, aniversários de eventos, revisão de metas, avanço de mercado tecnológico.
- **Década:** unidade usada para reflexão de legado, análise de era tecnológica e cálculo de conquistas de longuíssimo prazo (como NEXT LINUS).

O jogador pode, a qualquer momento, "avançar o tempo" em blocos (próximo dia, próxima semana, próximo mês, próximo ano) conforme configuração de rotina ativa. Durante o avanço automático, o sistema resolve internamente: progressão de conhecimento, produtividade em projetos, ganhos/perdas financeiras, mudanças de saúde/energia/estresse, eventos procedurais e reações do mundo.

### 2.2. Ciclo de decisão do jogador

Em cada "ponto de decisão" (que pode ser diário, semanal ou disparado por eventos), o jogador escolhe como alocar seu tempo disponível entre:

- Trabalho (se empregado ou freelancer)
- Estudo formal (curso, faculdade, pós, mestrado, doutorado)
- Estudo livre/autodidata (tecnologia específica, linguagem, tópico)
- Projetos pessoais (incluindo Open Source e GitHub)
- Criação de conteúdo (artigos, vídeos, palestras)
- Networking e relacionamento (mentoria, comunidade, eventos)
- Pesquisa acadêmica
- Empreendedorismo (construir/operar startup)
- Vida pessoal (descanso, saúde, relacionamentos pessoais, hobbies)

Cada alocação consome horas semanais disponíveis (definidas por energia, saúde, obrigações fixas como emprego/faculdade) e gera progresso incremental nos sistemas relevantes (conhecimento, reputação, dinheiro, satisfação, etc).

### 2.3. Ciclo de reação do mundo

Depois de cada avanço de tempo, o motor de simulação do mundo processa, de forma independente das ações do jogador:

1. Evolução do mercado de tecnologias (ascensão, estabilidade, declínio, obsolescência).
2. Evolução de empresas (crescimento, contração, fusões, falências, IPOs).
3. Evolução de NPCs (mudam de emprego, publicam projetos, ganham/perdem reputação, envelhecem, saem do mercado).
4. Geração de eventos, oportunidades e crises (ver Seção 10).
5. Atualização de oportunidades visíveis ao jogador (vagas de emprego, convites, propostas, chamadas de artigo, editais de pesquisa) com base no estado atual do jogador e do mundo.

---

---

# Índice completo

## Arquitetura

- [Arquitetura Técnica](architecture/ARCHITECTURE.md)
- [Persistência](architecture/PERSISTENCE.md)

## Sistemas e Mecânicas

- [Conhecimento e Habilidades](systems/SKILLS.md)
- [Educação Formal](systems/EDUCATION.md)
- [Projetos Pessoais, GitHub e Open Source](systems/PROJECTS.md)
- [Carreira, Empresas e Empregos](systems/CAREER.md)
- [Freelancing e Consultoria](systems/FREELANCE.md)
- [Networking, NPCs, Comunidades e Mentoria](systems/NETWORKING.md)
- [Conteúdo (Artigos, Vídeos, Palestras)](systems/CONTENT.md)
- [Pesquisa Acadêmica](systems/RESEARCH.md)
- [Empreendedorismo e Startups](systems/STARTUP.md)
- [Liderança e Gestão](systems/LEADERSHIP.md)
- [Reputação Multidimensional](systems/REPUTATION.md)
- [Sistema Financeiro](systems/FINANCE.md)
- [Vida Pessoal](systems/PERSONAL_LIFE.md)
- [Mercado de Tecnologia](systems/MARKET.md)
- [Eventos, Oportunidades e Crises](systems/EVENTS.md)
- [Achievements, Timeline e Legado](systems/ACHIEVEMENTS.md)

## Modelo e Regras

- [Entidades e Relacionamentos (Domain Model)](DOMAIN_MODEL.md)
- [Regras de Progressão e Interação entre Sistemas](PROGRESSION_RULES.md)

## Produto e Qualidade

- [UI/UX Multiplataforma (PC, Celular, Tablet)](UX.md)
- [Balanceamento](BALANCING.md)
- [Testes](TESTING.md)
- [Extensibilidade](EXTENSIBILITY.md)

## Planejamento

- [Ordem Recomendada de Implementação (Roadmap)](ROADMAP.md)
