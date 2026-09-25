# Sistema: Empreendedorismo e Startups

[Voltar para o índice](../SPEC.md)

## Sistemas relacionados

- [FINANCE](./FINANCE.md)
- [REPUTATION](./REPUTATION.md)
- [LEADERSHIP](./LEADERSHIP.md)
- [PROJECTS](./PROJECTS.md)
- [CONTENT](./CONTENT.md)

---

# Sistema de Empreendedorismo e Startups

**Objetivo:** modelar a criação, operação, crescimento ou falência de empreendimentos próprios.

**Regras:**
- Jogador pode fundar uma startup a partir de um projeto pessoal validado ou de uma ideia nova, exigindo capital inicial (próprio, investimento de terceiros, ou bootstrapping com renda paralela).
- Startup tem: estágio (ideação, MVP, tração, crescimento, escala, maturidade, encerramento), equipe (pode contratar NPCs), produto, métricas de negócio (usuários, receita, burn rate, runway) e saúde financeira própria, separada do patrimônio pessoal do jogador (mas ligada por investimento/retirada).
- Jogador que funda startup assume papel de **Founder**, podendo evoluir para CTO (se mantiver foco técnico) ou CEO (se assumir foco de negócio/liderança geral).
- Startups podem: crescer organicamente, receber rodadas de investimento (eventos gerados proceduralmente conforme tração), ser adquiridas por outra empresa, ou falir (drenando recursos e gerando forte impacto emocional/reputacional).
- Cofundadores e contratados (NPCs) trazem habilidades complementares mas também riscos de conflito, saída ou desempenho abaixo do esperado.

**Dados necessários:**
- Modelo de estágios de startup com métricas típicas por estágio.
- Modelo de eventos de investimento (probabilidade de captação por tração/reputação de negócios do jogador).
- Modelo de custo de equipe e produtividade de contratados.

**Interações:**
- Fortemente ligado ao sistema financeiro (risco/retorno).
- Alimenta reputação de negócios e liderança.
- Compete por tempo de forma intensa (startups geralmente exigem dedicação alta).
- Pode consumir/gerar projetos pessoais e conteúdo (divulgação do produto).

---

---

## Referências cruzadas

- Modelo de entidades relevantes: [DOMAIN_MODEL.md](../DOMAIN_MODEL.md)
- Regras de progressão e interação entre sistemas: [PROGRESSION_RULES.md](../PROGRESSION_RULES.md)
- Arquitetura e módulo correspondente: [architecture/ARCHITECTURE.md](../architecture/ARCHITECTURE.md)
- Ordem de implementação: [ROADMAP.md](../ROADMAP.md)
