# Sistema: Vida Pessoal (Saúde, Energia, Estresse, Satisfação)

[Voltar para o índice](../SPEC.md)

## Sistemas relacionados

- [CAREER](./CAREER.md)
- [FINANCE](./FINANCE.md)
- [SKILLS](./SKILLS.md)
- [CONTENT](./CONTENT.md)

---

# Sistema de Vida Pessoal (Saúde, Energia, Estresse, Satisfação)

**Objetivo:** modelar o bem-estar do personagem como recurso e como objetivo em si.

**Regras:**
- **Saúde:** afetada por rotina de trabalho excessiva, sono, exercício, alimentação (representados de forma simplificada por escolhas de estilo de vida). Saúde baixa aumenta risco de eventos negativos (doenças, esgotamento) que podem forçar pausas.
- **Energia:** recurso semanal renovável, consumido por todas as atividades; descanso insuficiente reduz energia disponível na semana seguinte.
- **Estresse:** acumula com sobrecarga (excesso de horas alocadas, crises, prazos apertados, conflitos); estresse alto reduz eficácia em todas as atividades e aumenta risco de burnout (evento que força afastamento).
- **Satisfação/felicidade:** métrica de "como o jogador está vivendo sua vida", influenciada por equilíbrio entre trabalho e vida pessoal, relacionamentos, realização de metas pessoais, e alinhamento entre valores do jogador e escolhas feitas.
- Vida pessoal inclui também relacionamentos não profissionais (família, parceiro(a), amigos fora do meio técnico), que podem gerar eventos próprios (casamento, filhos, cuidado de familiares) com impacto em tempo disponível e satisfação.

**Dados necessários:**
- Curvas de consumo/recuperação de energia.
- Curvas de acumulação/alívio de estresse.
- Modelo de eventos de vida pessoal (relacionamentos, família).

**Interações:** modula a eficácia de todos os outros sistemas (baixa energia/saúde/alta estresse reduz progresso em estudo, trabalho, projetos); é também um objetivo alternativo de "vitória" (jogador pode priorizar satisfação sobre carreira).

---

---

## Referências cruzadas

- Modelo de entidades relevantes: [DOMAIN_MODEL.md](../DOMAIN_MODEL.md)
- Regras de progressão e interação entre sistemas: [PROGRESSION_RULES.md](../PROGRESSION_RULES.md)
- Arquitetura e módulo correspondente: [architecture/ARCHITECTURE.md](../architecture/ARCHITECTURE.md)
- Ordem de implementação: [ROADMAP.md](../ROADMAP.md)
