[Voltar para o índice](SPEC.md)



---

# Entidades e Relacionamentos

Principais entidades do domínio (descritas conceitualmente, sem código):

- **Player** — estado central do personagem: atributos pessoais, referências para conhecimento, experiência, reputação, saúde/energia/estresse/satisfação, patrimônio, timeline, achievements desbloqueados.
- **SkillTree / SkillNode** — árvore de habilidades e nós individuais de tecnologia/competência, com nível e histórico de uso.
- **ExperienceRecord** — registros imutáveis de experiência acumulada (cargo, tecnologia, duração, contexto).
- **ReputationProfile** — conjunto das dimensões de reputação e seus valores/históricos.
- **EducationProgram / EducationEnrollment** — definição de programas educacionais e o vínculo do jogador com um programa específico (progresso, notas, status).
- **Project** — projeto pessoal/profissional, com estado, tecnologias, colaboradores, métricas (estrelas, receita, uso).
- **Repository** (especialização de Project voltada a Open Source) — métricas específicas de GitHub (estrelas, forks, issues, PRs, contribuidores).
- **Company** — empresa simulada, com porte, setor, cultura, saúde financeira, vagas.
- **JobPosition / Employment** — definição de cargo/vaga e o vínculo empregatício ativo/histórico do jogador com uma empresa.
- **InterviewProcess** — processo de entrevista em andamento, com etapas e resultados.
- **FreelanceContract** — contrato de projeto freelance/consultoria.
- **NPC** — personagem não jogável com trajetória própria e relacionamento com o jogador.
- **Relationship** — vínculo entre Player e NPC (tipo, força, histórico de interações).
- **Community** — comunidade temática e o vínculo de participação do jogador.
- **ContentPiece** — artigo, vídeo ou palestra produzido.
- **ResearchLine / Publication** — linha de pesquisa e publicações resultantes.
- **Startup** — empreendimento fundado pelo jogador, com estágio, equipe, métricas e saúde financeira própria.
- **FinancialAccount / Transaction** — saldo, investimentos, dívidas e histórico de transações.
- **LifeEvent** — evento de vida pessoal (relacionamento, família, saúde).
- **TechnologyMarketState** — estado do mercado para cada tecnologia ao longo do tempo.
- **WorldEvent / Opportunity / Crisis** — eventos gerados proceduralmente que afetam o jogador ou o mundo.
- **Achievement / AchievementProgress** — definição de conquista e progresso do jogador em relação a ela.
- **TimelineEntry** — entrada de linha do tempo.
- **GameClock** — estado atual de tempo simulado (dia/semana/mês/ano/década) e regras de avanço.
- **SaveGame** — agregado raiz de persistência representando o estado completo de uma partida.

### Relacionamentos principais

- Player 1—1 SkillTree, 1—1 ReputationProfile, 1—N ExperienceRecord.
- Player 1—N EducationEnrollment → N—1 EducationProgram.
- Player 1—N Project; Project 0—1 Repository (quando aplicável); Project N—N NPC (colaboradores).
- Player 1—N Employment → N—1 Company; Employment 1—N InterviewProcess (histórico de tentativas).
- Player 1—N FreelanceContract.
- Player 1—N Relationship → N—1 NPC.
- Player 1—N ContentPiece; Player 1—N ResearchLine → 1—N Publication.
- Player 0—N Startup (como founder); Startup 1—N Employment (equipe contratada, referenciando NPCs).
- Player 1—1 FinancialAccount → 1—N Transaction.
- Player 1—N LifeEvent.
- Player 1—N TimelineEntry; Player 1—N AchievementProgress → N—1 Achievement.
- GameClock 1—1 SaveGame (o relógio pertence ao estado salvo da partida).

---

---

## Onde cada entidade é discutida em profundidade

- **Player, SkillTree/SkillNode** → [systems/SKILLS.md](systems/SKILLS.md)
- **ExperienceRecord** → [systems/SKILLS.md](systems/SKILLS.md) (Seção 3.13)
- **ReputationProfile** → [systems/REPUTATION.md](systems/REPUTATION.md)
- **EducationProgram, EducationEnrollment** → [systems/EDUCATION.md](systems/EDUCATION.md)
- **Project, Repository** → [systems/PROJECTS.md](systems/PROJECTS.md)
- **Company, JobPosition, Employment, InterviewProcess** → [systems/CAREER.md](systems/CAREER.md)
- **FreelanceContract** → [systems/FREELANCE.md](systems/FREELANCE.md)
- **NPC, Relationship, Community** → [systems/NETWORKING.md](systems/NETWORKING.md)
- **ContentPiece** → [systems/CONTENT.md](systems/CONTENT.md)
- **ResearchLine, Publication** → [systems/RESEARCH.md](systems/RESEARCH.md)
- **Startup** → [systems/STARTUP.md](systems/STARTUP.md)
- **FinancialAccount, Transaction** → [systems/FINANCE.md](systems/FINANCE.md)
- **LifeEvent** → [systems/PERSONAL_LIFE.md](systems/PERSONAL_LIFE.md)
- **TechnologyMarketState** → [systems/MARKET.md](systems/MARKET.md)
- **WorldEvent, Opportunity, Crisis** → [systems/EVENTS.md](systems/EVENTS.md)
- **Achievement, AchievementProgress, TimelineEntry** → [systems/ACHIEVEMENTS.md](systems/ACHIEVEMENTS.md)
- **GameClock, SaveGame** → [architecture/PERSISTENCE.md](architecture/PERSISTENCE.md) e [architecture/ARCHITECTURE.md](architecture/ARCHITECTURE.md)
