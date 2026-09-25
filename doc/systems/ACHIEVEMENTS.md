# Sistema: Achievements, Timeline e Legado

[Voltar para o índice](../SPEC.md)

## Sistemas relacionados

- [PROJECTS](./PROJECTS.md)
- [REPUTATION](./REPUTATION.md)
- [RESEARCH](./RESEARCH.md)
- [STARTUP](./STARTUP.md)
- [LEADERSHIP](./LEADERSHIP.md)

---

# Sistema de Achievements, Timeline e Legado

**Objetivo:** registrar a história única de cada jogador e reconhecer marcos extraordinários.

**Regras:**
- **Timeline:** registro cronológico de todos os eventos relevantes da carreira/vida do jogador (formaturas, empregos, demissões, projetos lançados, publicações, relacionamentos, crises superadas), navegável e exportável.
- **Achievements:** conquistas categorizadas por raridade (comum, incomum, raro, épico, lendário), cobrindo todas as áreas do jogo (técnica, acadêmica, negócios, liderança, vida pessoal, open source).
- Achievements lendários exigem combinações extremas de múltiplos sistemas sustentadas por longos períodos (décadas), não apenas um pico isolado.
- **NEXT LINUS** (achievement lendário máximo, ligado a Open Source): exige que o jogador mantenha, por décadas, um projeto Open Source que se torne infraestrutura crítica global — combinando: impacto Open Source no nível máximo sustentado por no mínimo ~20 anos simulados, reputação técnica e de comunidade no nível máximo, número mínimo de projetos/empresas dependentes do trabalho do jogador acima de um limiar altíssimo (definido em dados de balanceamento), reconhecimento por múltiplos NPCs de peso no mundo do jogo, e nenhum período de abandono prolongado do projeto principal. É deliberadamente quase inatingível na prática, refletindo a raridade de um impacto desse porte no mundo real.
- **Legado:** ao final de uma partida (por escolha do jogador, não por condição de derrota), o jogo gera um resumo narrativo e estatístico da trajetória completa, incluindo o que "ficou" (projetos ainda ativos, pessoas mentoradas, empresas fundadas, publicações, impacto estimado).

**Dados necessários:**
- Catálogo completo de achievements com critérios formais (expressões sobre variáveis de estado do jogador ao longo do tempo).
- Template de geração de resumo de legado.

**Interações:** transversal; consome dados de todos os outros sistemas para avaliar critérios.

---

---

## Referências cruzadas

- Modelo de entidades relevantes: [DOMAIN_MODEL.md](../DOMAIN_MODEL.md)
- Regras de progressão e interação entre sistemas: [PROGRESSION_RULES.md](../PROGRESSION_RULES.md)
- Arquitetura e módulo correspondente: [architecture/ARCHITECTURE.md](../architecture/ARCHITECTURE.md)
- Ordem de implementação: [ROADMAP.md](../ROADMAP.md)
