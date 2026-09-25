# Sistema: Conhecimento e Habilidades

[Voltar para o índice](../SPEC.md)

## Sistemas relacionados

- [CAREER](./CAREER.md)
- [PROJECTS](./PROJECTS.md)
- [EDUCATION](./EDUCATION.md)
- [REPUTATION](./REPUTATION.md)
- [RESEARCH](./RESEARCH.md)

---

# Sistema de Conhecimento e Habilidades

**Objetivo:** modelar o que o personagem sabe fazer, com granularidade suficiente para diferenciar trajetórias (ex.: Backend Java vs Backend Go vs Mobile Kotlin).

**Regras:**
- Conhecimento é organizado em **árvore de habilidades por área** (Backend, Frontend, Mobile, Games, Embedded, Data, AI/ML, Cloud/DevOps, Security, Research, e áreas adicionais definidas por dados).
- Cada área contém **tecnologias/linguagens específicas** (ex.: dentro de Backend: Java, Go, Node.js, C#, Python) e **competências transversais** (ex.: arquitetura de sistemas, testes, design de APIs).
- Cada habilidade tem um **nível numérico** (ex.: 0 a 100, ou faixas: Iniciante, Júnior, Pleno, Sênior, Especialista, Referência Mundial).
- Habilidades sobem por: estudo dedicado, prática em projetos reais, uso no trabalho, mentoria recebida, ensino (ensinar reforça o próprio conhecimento).
- Habilidades **decaem lentamente por desuso** (tecnologia não utilizada há anos perde relevância prática, embora nunca chegue a zero — representa memória residual).
- Existe uma métrica agregada de **"amplitude" vs "profundidade"**: jogadores generalistas têm muitas habilidades em nível médio; especialistas têm poucas habilidades em nível altíssimo. Isso afeta elegibilidade para determinados cargos/eventos (ex.: Staff Engineer exige profundidade; Architect exige amplitude).

**Dados necessários:**
- Catálogo de áreas técnicas.
- Catálogo de tecnologias/linguagens por área, com metadados: ano de criação (fictício ou realista), curva de popularidade ao longo do tempo, dificuldade de aprendizado, pré-requisitos (ex.: TypeScript exige JavaScript básico).
- Catálogo de competências transversais.
- Tabela de curva de XP necessária por nível.

**Interações:**
- Alimenta elegibilidade para vagas de emprego, propostas de projeto, convites de palestra, aceite em programas de pós-graduação.
- Alimenta a velocidade e qualidade de produção em projetos pessoais e Open Source.
- Alimenta reputação técnica quando aplicada publicamente (commits, artigos, palestras).

**Exemplo de comportamento:** um jogador que estuda Java por 3 anos consecutivos e trabalha profissionalmente com Spring Boot atinge nível "Especialista" em Java Backend; se parar de usar por 5 anos migrando para Frontend, o nível de Java decai gradualmente para "Sênior" e se estabiliza, nunca desaparecendo.

---

---

# Sistema de Conhecimento vs. Experiência vs. Reputação (separação explícita)

Para reforçar a exigência do projeto, os três sistemas são modelados como entidades e tabelas separadas:

- **Conhecimento:** níveis de habilidade por tecnologia/competência (Seção 3.1). Representa capacidade teórica/prática.
- **Experiência:** acumulado de tempo e contexto de aplicação real (anos em determinado cargo, anos usando determinada tecnologia em produção, número de projetos entregues, número de crises técnicas resolvidas). Não decai; é histórico permanente. Usada como pré-requisito para cargos sênior/avançados independentemente do nível puro de habilidade.
- **Reputação:** percepção pública multidimensional (Seção 3.12). Decai por inatividade; é o que abre portas externas (convites, ofertas, indicações).

Essas três dimensões interagem mas nunca se fundem em uma métrica única, permitindo arquétipos como "muito conhecimento, pouca experiência" (autodidata teórico) ou "muita experiência, pouca reputação" (veterano discreto).

---

---

## Referências cruzadas

- Modelo de entidades relevantes: [DOMAIN_MODEL.md](../DOMAIN_MODEL.md)
- Regras de progressão e interação entre sistemas: [PROGRESSION_RULES.md](../PROGRESSION_RULES.md)
- Arquitetura e módulo correspondente: [architecture/ARCHITECTURE.md](../architecture/ARCHITECTURE.md)
- Ordem de implementação: [ROADMAP.md](../ROADMAP.md)
