# Sistema: Sistema Financeiro

[Voltar para o índice](../SPEC.md)

## Sistemas relacionados

- [CAREER](./CAREER.md)
- [FREELANCE](./FREELANCE.md)
- [STARTUP](./STARTUP.md)
- [EDUCATION](./EDUCATION.md)
- [PERSONAL_LIFE](./PERSONAL_LIFE.md)

---

# Sistema Financeiro

**Objetivo:** modelar dinheiro, patrimônio e despesas do jogador.

**Regras:**
- Fontes de renda: salário, freelance, consultoria, monetização de conteúdo, dividendos/retorno de startup, royalties de projetos.
- Despesas: custo de vida (moradia, alimentação, transporte — variam por região/estilo de vida escolhido), educação (mensalidades), saúde (tratamentos), investimentos em projetos/startup, lazer.
- Patrimônio inclui: saldo líquido, investimentos financeiros simples (renda fixa/variável simulada de forma simplificada), participação societária em startups (valorização/desvalorização ao longo do tempo).
- Jogador pode contrair dívidas (empréstimos, financiamento educacional) com juros e prazos.
- Eventos financeiros procedurais: crises econômicas (afetam mercado de trabalho e investimentos), oportunidades de investimento, imprevistos (despesas inesperadas).

**Dados necessários:**
- Tabela de custo de vida por região/padrão de vida.
- Modelo simplificado de rentabilidade de investimentos.
- Modelo de juros para dívidas.

**Interações:** conectado a praticamente todos os sistemas que geram custo ou renda (educação, projetos, startups, freelance, carreira).

---

---

## Referências cruzadas

- Modelo de entidades relevantes: [DOMAIN_MODEL.md](../DOMAIN_MODEL.md)
- Regras de progressão e interação entre sistemas: [PROGRESSION_RULES.md](../PROGRESSION_RULES.md)
- Arquitetura e módulo correspondente: [architecture/ARCHITECTURE.md](../architecture/ARCHITECTURE.md)
- Ordem de implementação: [ROADMAP.md](../ROADMAP.md)
