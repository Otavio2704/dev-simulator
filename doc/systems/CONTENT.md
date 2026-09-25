# Sistema: Conteúdo (Artigos, Vídeos, Palestras)

[Voltar para o índice](../SPEC.md)

## Sistemas relacionados

- [REPUTATION](./REPUTATION.md)
- [NETWORKING](./NETWORKING.md)
- [CAREER](./CAREER.md)
- [FREELANCE](./FREELANCE.md)

---

# Sistema de Conteúdo (Artigos, Vídeos, Palestras)

**Objetivo:** modelar produção de conteúdo técnico como forma de construir reputação e renda.

**Regras:**
- Jogador pode produzir: artigos escritos, vídeos técnicos, palestras em eventos (locais, nacionais, internacionais).
- Cada peça de conteúdo tem: tema (ligado a uma área/tecnologia), qualidade (baseada em habilidade + tempo investido), alcance (baseado em reputação de conteúdo prévia + divulgação em comunidades) e recepção (métrica de sucesso).
- Conteúdo de sucesso aumenta reputação de conteúdo e, secundariamente, reputação técnica na área abordada.
- Convites para palestrar em eventos maiores exigem reputação de conteúdo/técnica mínima; palestras de peso (ex. keynote internacional) são eventos raros gerados proceduralmente quando o jogador atinge certos patamares.
- Produção de conteúdo consistente ao longo de anos pode consolidar a trilha de carreira de **Developer Advocate**.

**Dados necessários:**
- Catálogo de formatos de conteúdo com custo de tempo e curva de alcance.
- Catálogo de eventos (meetup, conferência nacional, conferência internacional) com requisitos de reputação para convite/aceite de submissão.

**Interações:**
- Alimenta reputação de conteúdo e técnica.
- Alimenta networking (conteúdo bom atrai contatos).
- Pode gerar renda direta (monetização) ou indireta (leads de freelance/consultoria/emprego).

---

---

## Referências cruzadas

- Modelo de entidades relevantes: [DOMAIN_MODEL.md](../DOMAIN_MODEL.md)
- Regras de progressão e interação entre sistemas: [PROGRESSION_RULES.md](../PROGRESSION_RULES.md)
- Arquitetura e módulo correspondente: [architecture/ARCHITECTURE.md](../architecture/ARCHITECTURE.md)
- Ordem de implementação: [ROADMAP.md](../ROADMAP.md)
