# Sistema: Educação Formal

[Voltar para o índice](../SPEC.md)

## Sistemas relacionados

- [SKILLS](./SKILLS.md)
- [CAREER](./CAREER.md)
- [RESEARCH](./RESEARCH.md)
- [REPUTATION](./REPUTATION.md)
- [FINANCE](./FINANCE.md)

---

# Sistema de Educação Formal

**Objetivo:** modelar faculdade, cursos livres, pós-graduação, mestrado e doutorado como trilhas de longo prazo com custo, tempo e retorno.

**Regras:**
- Cada programa educacional tem: duração (em meses/anos), custo, requisito de entrada (ex.: mestrado exige graduação concluída + reputação acadêmica mínima), carga horária semanal exigida, e habilidades/reputação geradas ao concluir.
- Programas podem ser **concluídos, trancados (pausados) ou abandonados**, cada um com consequências diferentes (ex.: abandono gera pequena penalidade de reputação; trancamento permite retomar depois).
- Desempenho acadêmico (baseado em horas dedicadas e habilidades de base) gera uma **nota final**, que influencia oportunidades futuras (ex.: bolsa de doutorado, convite para programa de pesquisa).
- Doutorado e mestrado alimentam diretamente a dimensão de **reputação acadêmica** e desbloqueiam carreira de Pesquisador/Professor.

**Dados necessários:**
- Catálogo de instituições fictícias (com prestígio variável).
- Catálogo de programas (graduação, curso técnico, curso livre, pós lato sensu, mestrado, doutorado, pós-doutorado) com custo, duração, requisitos e recompensas.

**Interações:**
- Requisito de entrada em determinadas carreiras (Researcher, Professor exigem doutorado; algumas vagas de Cloud/Security preferem certificações).
- Consome tempo semanal, competindo diretamente com trabalho e projetos pessoais.
- Gera dívida ou consome patrimônio (sistema financeiro).

**Exemplo de comportamento:** jogador entra em mestrado em Ciência da Computação aos 24 anos, dedicando 20h/semana por 2 anos; ao concluir, ganha grande incremento em reputação acadêmica e desbloqueia elegibilidade para vagas de Pesquisa em empresas e editais de doutorado com bolsa.

---

---

## Referências cruzadas

- Modelo de entidades relevantes: [DOMAIN_MODEL.md](../DOMAIN_MODEL.md)
- Regras de progressão e interação entre sistemas: [PROGRESSION_RULES.md](../PROGRESSION_RULES.md)
- Arquitetura e módulo correspondente: [architecture/ARCHITECTURE.md](../architecture/ARCHITECTURE.md)
- Ordem de implementação: [ROADMAP.md](../ROADMAP.md)
