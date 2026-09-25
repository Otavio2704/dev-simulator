# Sistema: Carreira, Empresas e Empregos

[Voltar para o índice](../SPEC.md)

## Sistemas relacionados

- [SKILLS](./SKILLS.md)
- [REPUTATION](./REPUTATION.md)
- [FINANCE](./FINANCE.md)
- [NETWORKING](./NETWORKING.md)
- [MARKET](./MARKET.md)
- [LEADERSHIP](./LEADERSHIP.md)

---

# Sistema de Carreira, Empresas e Empregos

**Objetivo:** modelar vínculos empregatícios, cargos, promoções, demissões, entrevistas e a estrutura corporativa que o jogador atravessa.

**Regras:**
- Empresas têm: porte (startup, scale-up, média, grande, multinacional), setor, cultura (ex.: alta pressão, equilíbrio de vida, inovação, conservadora), saúde financeira (que evolui independentemente) e vagas abertas geradas proceduralmente.
- Cargos seguem trilhas técnicas e de gestão, incluindo os avançados: Junior/Pleno/Senior Engineer, Staff Engineer, Principal Engineer, Distinguished Engineer, Architect, Tech Lead, Engineering Manager, Director, VP Engineering, CTO, além de trilhas alternativas como Developer Advocate, Open Source Maintainer (remunerado), Consultant, Researcher (em empresa) e Founder.
- Cada cargo tem requisitos mínimos de habilidade, reputação (nas dimensões relevantes) e experiência acumulada (anos em cargos anteriores).
- **Processo de entrevista** é um mini-sistema próprio: cada entrevista simula etapas (triagem, técnica, comportamental, com liderança), cada etapa com chance de sucesso baseada em habilidades relevantes, preparação prévia (tempo investido estudando para a entrevista) e um fator de variância (representando sorte/dia ruim/dia bom).
- Salário é definido por cargo, empresa, região simulada, habilidades e resultado de negociação (o jogador pode negociar, com risco de perder a oferta se pedir demais sem lastro).
- Avaliação de desempenho periódica pode gerar: aumento salarial, promoção, PIP (plano de melhoria), ou demissão.
- Jogador pode ser demitido por: baixo desempenho sustentado, crise na empresa (corte de custos), ou eventos de mercado (Seção 10).
- Jogador pode pedir demissão a qualquer momento, com custos de transição (período sem renda, impacto emocional).

**Dados necessários:**
- Catálogo de empresas geradas proceduralmente (nome, setor, porte, cultura, saúde financeira inicial).
- Catálogo de cargos e requisitos por trilha.
- Tabelas salariais base por cargo/região/porte de empresa.
- Modelo de etapas de entrevista com pesos de habilidades por etapa.

**Interações:**
- Consome a maior parte do tempo semanal do jogador enquanto empregado.
- Alimenta renda (sistema financeiro), reputação técnica/liderança/negócios, e experiência de carreira.
- Interage com rede de contatos (indicações aumentam chance de entrevista).

**Exemplo de comportamento:** jogador com 8 anos de experiência em Backend Java, reputação técnica alta e 2 indicações de ex-colegas se candidata a Staff Engineer em uma empresa grande; passa por 4 etapas de entrevista ao longo de 6 semanas, cada uma consumindo tempo de preparo; sucesso depende de habilidade técnica, comunicação e sorte.

---

---

## Referências cruzadas

- Modelo de entidades relevantes: [DOMAIN_MODEL.md](../DOMAIN_MODEL.md)
- Regras de progressão e interação entre sistemas: [PROGRESSION_RULES.md](../PROGRESSION_RULES.md)
- Arquitetura e módulo correspondente: [architecture/ARCHITECTURE.md](../architecture/ARCHITECTURE.md)
- Ordem de implementação: [ROADMAP.md](../ROADMAP.md)
