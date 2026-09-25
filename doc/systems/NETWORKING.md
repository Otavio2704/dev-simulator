# Sistema: Networking, NPCs, Comunidades e Mentoria

[Voltar para o índice](../SPEC.md)

## Sistemas relacionados

- [REPUTATION](./REPUTATION.md)
- [CAREER](./CAREER.md)
- [PROJECTS](./PROJECTS.md)
- [CONTENT](./CONTENT.md)
- [STARTUP](./STARTUP.md)
- [SKILLS](./SKILLS.md)

---

# Sistema de Networking, NPCs, Comunidades e Mentoria

**Objetivo:** modelar relações interpessoais que influenciam oportunidades, conhecimento e suporte emocional.

**Regras:**
- NPCs são gerados com: nome, trajetória de carreira própria (que evolui com o tempo), personalidade, especialidades técnicas, e nível de relacionamento com o jogador (desconhecido, conhecido, contato, colega, amigo, mentor/mentorado, referência).
- Relacionamentos evoluem por: interações diretas (eventos, colaboração em projeto, mesma empresa), tempo de convivência, e ações deliberadas de networking (participar de comunidades, eventos, meetups, conferências).
- NPCs podem: recomendar o jogador para vagas, convidar para projetos, oferecer mentoria (acelera ganho de habilidade/reputação), pedir ajuda (gerando reciprocidade), ou se afastar por negligência do relacionamento.
- Comunidades (grupos temáticos, ex. comunidade de Java, comunidade de IA) têm reputação própria; participação ativa e contribuição aumentam a reputação de comunidade do jogador.
- Jogador pode se tornar mentor de outros (incluindo NPCs juniores), o que consome tempo mas gera reputação de comunidade/liderança e satisfação pessoal.

**Dados necessários:**
- Gerador procedural de NPCs (nomes, arquétipos de personalidade, especialidades).
- Modelo de evolução de carreira de NPC (simplificado, reaproveitando parte do sistema de carreira do jogador).
- Catálogo de comunidades temáticas e eventos recorrentes (meetups, conferências).

**Interações:**
- Alimenta reputação de comunidade.
- Alimenta oportunidades de emprego, projetos, palestras e parcerias de startup.
- Pode gerar eventos pessoais (amizades, conflitos, parcerias, rivalidades).

**Exemplo de comportamento:** jogador frequenta meetups de Go por 2 anos, cultiva relação de "amigo" com 3 NPCs da comunidade; um deles, ao ser promovido a gerente em uma empresa, indica o jogador diretamente para uma vaga, pulando etapas de triagem.

---

---

## Referências cruzadas

- Modelo de entidades relevantes: [DOMAIN_MODEL.md](../DOMAIN_MODEL.md)
- Regras de progressão e interação entre sistemas: [PROGRESSION_RULES.md](../PROGRESSION_RULES.md)
- Arquitetura e módulo correspondente: [architecture/ARCHITECTURE.md](../architecture/ARCHITECTURE.md)
- Ordem de implementação: [ROADMAP.md](../ROADMAP.md)
