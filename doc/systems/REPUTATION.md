# Sistema: Reputação Multidimensional

[Voltar para o índice](../SPEC.md)

## Sistemas relacionados

- [SKILLS](./SKILLS.md)
- [PROJECTS](./PROJECTS.md)
- [NETWORKING](./NETWORKING.md)
- [RESEARCH](./RESEARCH.md)
- [CONTENT](./CONTENT.md)
- [STARTUP](./STARTUP.md)
- [LEADERSHIP](./LEADERSHIP.md)
- [ACHIEVEMENTS](./ACHIEVEMENTS.md)

---

# Sistema de Reputação Multidimensional

**Objetivo:** representar como o jogador é percebido pelo mundo, de forma multifacetada, evitando uma única métrica de "fama".

**Regras:**
- Dimensões de reputação, cada uma numérica e independente:
  - **Técnica** (competência reconhecida na prática de engenharia)
  - **Open Source** (impacto e contribuição em projetos públicos)
  - **Comunidade** (presença e contribuição em comunidades/eventos)
  - **Acadêmica** (produção científica e reconhecimento em pesquisa)
  - **Conteúdo** (alcance e qualidade como criador de conteúdo)
  - **Negócios** (sucesso e credibilidade em empreendedorismo/estratégia)
  - **Liderança** (capacidade reconhecida de liderar pessoas/times)
- Cada dimensão sobe por ações específicas descritas nos sistemas correspondentes, e decai lentamente por inatividade prolongada.
- Reputação é **explicitamente diferente de Conhecimento e de Experiência**: conhecimento é "o que a pessoa sabe fazer", experiência é "quanto tempo/contextos ela praticou", reputação é "o que o mundo reconhece publicamente sobre ela" — um jogador pode ter conhecimento alto e reputação baixa (gênio anônimo) ou o inverso (reputação inflada além da competência real, o que gera risco de "queda" ao ser testado).
- Reputação combinada (todas as dimensões) determina elegibilidade para achievements lendários e para os cargos/eventos mais raros do jogo.

**Dados necessários:**
- Pesos de conversão de cada ação de cada sistema para a dimensão de reputação correspondente.
- Curvas de decaimento por dimensão.

**Interações:** transversal a praticamente todos os sistemas; é a principal "moeda social" do jogo.

---

---

## Referências cruzadas

- Modelo de entidades relevantes: [DOMAIN_MODEL.md](../DOMAIN_MODEL.md)
- Regras de progressão e interação entre sistemas: [PROGRESSION_RULES.md](../PROGRESSION_RULES.md)
- Arquitetura e módulo correspondente: [architecture/ARCHITECTURE.md](../architecture/ARCHITECTURE.md)
- Ordem de implementação: [ROADMAP.md](../ROADMAP.md)
