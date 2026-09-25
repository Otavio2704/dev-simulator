# Sistema: Projetos Pessoais, GitHub e Open Source

[Voltar para o índice](../SPEC.md)

## Sistemas relacionados

- [SKILLS](./SKILLS.md)
- [REPUTATION](./REPUTATION.md)
- [CAREER](./CAREER.md)
- [FREELANCE](./FREELANCE.md)
- [STARTUP](./STARTUP.md)
- [ACHIEVEMENTS](./ACHIEVEMENTS.md)
- [NETWORKING](./NETWORKING.md)

---

# Sistema de Projetos Pessoais

**Objetivo:** modelar a criação, manutenção e evolução de projetos de software feitos por iniciativa do jogador, sejam privados, públicos ou comerciais.

**Regras:**
- Um projeto tem: tipo (aprendizado, portfólio, open source, produto comercial, pesquisa), tecnologias usadas, complexidade, tempo estimado de desenvolvimento, e estado (planejamento, em desenvolvimento, lançado, mantido, abandonado, arquivado).
- Progresso de projeto depende de horas investidas por período e do nível de habilidade nas tecnologias envolvidas.
- Projetos podem gerar: aumento de habilidade nas tecnologias usadas, reputação técnica, reputação open source (se publicado), renda (se monetizado), leads de emprego ou clientes freelance, materiais para conteúdo (artigos sobre o projeto).
- Projetos abandonados no meio do caminho geram penalidade leve de reputação/moral, mas nem sempre são negativos (podem ter servido de aprendizado).
- Projetos podem receber **contribuições de NPCs** (colaboradores) se forem públicos e tiverem reputação suficiente para atrair colaboradores.

**Dados necessários:**
- Templates de tipos de projeto com faixas de complexidade e tempo.
- Tabela de conversão "horas investidas + habilidade" → "qualidade do projeto resultante".

**Interações:**
- Integra com GitHub/Open Source (Seção 3.4).
- Alimenta portfólio, usado em entrevistas de emprego e propostas de freelance.
- Pode virar produto de uma startup (Seção 3.10).

**Exemplo de comportamento:** jogador cria uma biblioteca open source de manipulação de datas em Go; investe 5h/semana por 8 meses; ao publicar no GitHub, ganha estrelas ao longo do tempo proporcionalmente à qualidade e à divulgação (conteúdo/networking), aumentando reputação open source e eventualmente sendo notado por uma empresa que usa a biblioteca.

---

---

# Sistema de GitHub e Open Source

**Objetivo:** simular presença pública em plataformas de código, contribuições a projetos de terceiros e manutenção de projetos próprios.

**Regras:**
- Perfil público do jogador acumula: repositórios próprios, contribuições externas (PRs aceitas em projetos de terceiros/NPCs), estrelas, seguidores, issues resolvidas.
- Contribuir para projetos de terceiros (incluindo projetos de NPCs e "projetos históricos" simulados, como frameworks fictícios de grande porte) exige nível mínimo de habilidade e gera reputação open source proporcional à relevância do projeto.
- Manter um projeto próprio popular exige tempo contínuo (responder issues, revisar PRs de colaboradores, lançar versões); negligenciar um projeto popular por muito tempo reduz sua relevância e pode gerar "forks" que ultrapassam o projeto original.
- Existe uma métrica de **impacto open source** (diferente de popularidade pura) que considera: quantos outros projetos/empresas dependem do trabalho do jogador, tempo de manutenção contínua, e menções por NPCs relevantes.

**Dados necessários:**
- Catálogo de "projetos históricos" do universo do jogo (equivalentes fictícios a frameworks/linguagens famosas) que podem receber contribuições.
- Curva de crescimento orgânico de estrelas/seguidores por qualidade e divulgação.

**Interações:**
- Base para achievements lendários (incluindo NEXT LINUS).
- Alimenta reputação open source, uma das dimensões centrais de reputação.
- Pode gerar convites de emprego, palestras e mentorias.

**Exemplo de comportamento:** jogador mantém por 15 anos consecutivos um projeto que se torna dependência crítica de milhares de outros projetos simulados; isso é rastreado como pré-condição para o achievement NEXT LINUS.

---

---

## Referências cruzadas

- Modelo de entidades relevantes: [DOMAIN_MODEL.md](../DOMAIN_MODEL.md)
- Regras de progressão e interação entre sistemas: [PROGRESSION_RULES.md](../PROGRESSION_RULES.md)
- Arquitetura e módulo correspondente: [architecture/ARCHITECTURE.md](../architecture/ARCHITECTURE.md)
- Ordem de implementação: [ROADMAP.md](../ROADMAP.md)
