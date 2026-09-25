# Sistema: Pesquisa Acadêmica

[Voltar para o índice](../SPEC.md)

## Sistemas relacionados

- [EDUCATION](./EDUCATION.md)
- [REPUTATION](./REPUTATION.md)
- [CAREER](./CAREER.md)
- [STARTUP](./STARTUP.md)

---

# Sistema de Pesquisa Acadêmica

**Objetivo:** modelar produção científica, publicações e carreira acadêmica.

**Regras:**
- Disponível a partir de vínculo com programa de pós-graduação (mestrado/doutorado) ou posição de pesquisa em empresa/instituição.
- Jogador conduz **linhas de pesquisa** (ligadas a uma área, ex. AI/ML, Segurança), que avançam com tempo investido e habilidade técnica/teórica.
- Pesquisa gera **publicações**, cada uma com relevância (baseada em qualidade da pesquisa + reputação acadêmica do jogador + relevância do veículo de publicação), citações ao longo do tempo (crescem organicamente, influenciadas por reputação e divulgação) e contribuição para reputação acadêmica.
- Carreira de **Researcher** e **Professor** dependem fortemente dessa dimensão; orientação de outros pesquisadores (NPCs juniores) é uma extensão do sistema de mentoria.

**Dados necessários:**
- Catálogo de linhas de pesquisa por área.
- Catálogo de veículos de publicação (conferências, journals) com prestígio variável.
- Curva de acumulação de citações ao longo do tempo.

**Interações:**
- Alimenta reputação acadêmica.
- Pode gerar convites para cargos de professor/pesquisador em instituições.
- Pode alimentar inovação em startups (pesquisa aplicada virando produto).

---

---

## Referências cruzadas

- Modelo de entidades relevantes: [DOMAIN_MODEL.md](../DOMAIN_MODEL.md)
- Regras de progressão e interação entre sistemas: [PROGRESSION_RULES.md](../PROGRESSION_RULES.md)
- Arquitetura e módulo correspondente: [architecture/ARCHITECTURE.md](../architecture/ARCHITECTURE.md)
- Ordem de implementação: [ROADMAP.md](../ROADMAP.md)
