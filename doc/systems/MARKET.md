# Sistema: Mercado de Tecnologia

[Voltar para o índice](../SPEC.md)

## Sistemas relacionados

- [CAREER](./CAREER.md)
- [SKILLS](./SKILLS.md)
- [EVENTS](./EVENTS.md)

---

# Sistema de Mercado de Tecnologia

**Objetivo:** simular a evolução do cenário tecnológico ao longo de décadas, criando ascensão e queda de tecnologias, linguagens e paradigmas.

**Regras:**
- Cada tecnologia tem um ciclo de vida procedural: surgimento, crescimento, pico, estabilização/declínio, obsolescência (ou "tecnologia legada eterna", para simular casos como COBOL).
- O ciclo é influenciado por eventos de mercado (adoção por grandes empresas simuladas, tendências geradas proceduralmente) e, em menor grau, pelas ações agregadas dos jogadores/NPCs (efeito de comunidade).
- A demanda de mercado por tecnologia afeta: número de vagas disponíveis, faixas salariais, e relevância de habilidades para reputação técnica.
- Novas tecnologias podem ser geradas proceduralmente ao longo das décadas, representando a inovação contínua do setor (via dados configuráveis, sem necessidade de codificação).

**Dados necessários:**
- Modelo de ciclo de vida de tecnologia (curva de popularidade ao longo do tempo).
- Gerador procedural de novas tecnologias (nome, área, características herdadas de tecnologias "parentes").

**Interações:** afeta diretamente o sistema de carreira (vagas/salários), o sistema de conhecimento (relevância de habilidades) e a geração de eventos.

---

---

## Referências cruzadas

- Modelo de entidades relevantes: [DOMAIN_MODEL.md](../DOMAIN_MODEL.md)
- Regras de progressão e interação entre sistemas: [PROGRESSION_RULES.md](../PROGRESSION_RULES.md)
- Arquitetura e módulo correspondente: [architecture/ARCHITECTURE.md](../architecture/ARCHITECTURE.md)
- Ordem de implementação: [ROADMAP.md](../ROADMAP.md)
