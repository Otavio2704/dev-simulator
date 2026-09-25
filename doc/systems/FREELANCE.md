# Sistema: Freelancing e Consultoria

[Voltar para o índice](../SPEC.md)

## Sistemas relacionados

- [FINANCE](./FINANCE.md)
- [CAREER](./CAREER.md)
- [PROJECTS](./PROJECTS.md)
- [REPUTATION](./REPUTATION.md)

---

# Sistema de Freelancing e Consultoria

**Objetivo:** modelar trabalho autônomo como alternativa ou complemento ao emprego formal.

**Regras:**
- Jogador pode aceitar projetos freelance de clientes gerados proceduralmente (indivíduos, pequenas empresas, startups), cada um com escopo, prazo, pagamento e risco de cancelamento/calote.
- Consultoria é uma forma avançada de freelance, disponível a partir de determinado nível de reputação técnica/negócios, com tickets mais altos e menos volume.
- Reputação em freelancing (confiabilidade, qualidade entregue, cumprimento de prazo) afeta o fluxo futuro de propostas e os valores oferecidos.
- Freelancing pode ser feito em paralelo a um emprego formal (com limite de horas/energia) ou como ocupação principal.

**Dados necessários:**
- Catálogo de tipos de projeto freelance com faixas de escopo/prazo/pagamento.
- Curva de reputação-para-fluxo-de-propostas.

**Interações:**
- Alimenta sistema financeiro diretamente.
- Compete por tempo com emprego, estudo e projetos pessoais.
- Pode alimentar portfólio e, eventualmente, virar uma consultoria estabelecida ou startup.

---

---

## Referências cruzadas

- Modelo de entidades relevantes: [DOMAIN_MODEL.md](../DOMAIN_MODEL.md)
- Regras de progressão e interação entre sistemas: [PROGRESSION_RULES.md](../PROGRESSION_RULES.md)
- Arquitetura e módulo correspondente: [architecture/ARCHITECTURE.md](../architecture/ARCHITECTURE.md)
- Ordem de implementação: [ROADMAP.md](../ROADMAP.md)
