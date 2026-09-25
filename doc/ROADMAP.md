[Voltar para o índice](SPEC.md)



---

# Ordem Recomendada de Implementação

A ordem abaixo busca permitir validação incremental do núcleo de simulação antes de camadas dependentes, sem nunca reduzir o escopo final descrito neste documento — cada fase entrega uma fatia vertical completa (domínio + persistência + API mínima) de um subconjunto de sistemas, não uma versão simplificada permanente deles.

1. **Fundação técnica:** setup de projeto Maven multi-módulo, configuração Spring Boot 3/WebFlux, integração PostgreSQL via Spring Data, Docker Compose para ambiente local, pipeline inicial GitHub Actions com testes e SonarQube, estrutura base de OpenAPI.
2. **Núcleo de tempo e estado do jogador:** `core-time` (GameClock e avanço de tempo), entidade `Player` mínima, `SaveGame` e persistência básica (save/load simples, sem ainda todos os subsistemas).
3. **Sistema de Conhecimento e Habilidades** (`core-skills`), incluindo carregamento data-driven do catálogo de tecnologias/áreas.
4. **Sistema de Experiência** (`core-experience`) e **Sistema de Reputação Multidimensional** (`core-reputation`), estabelecendo a separação conceitual central do jogo (Seção 3.13) desde cedo.
5. **Sistema Financeiro** (`core-finance`) e **Sistema de Vida Pessoal** (`core-personal-life`), pois modulam e são modulados por praticamente todos os sistemas subsequentes.
6. **Sistema de Mercado de Tecnologia** (`core-market`), base necessária para carreira e eventos realistas.
7. **Sistema de Carreira, Empresas e Empregos** (`core-career`), incluindo processo de entrevistas.
8. **Sistema de Projetos Pessoais** e **GitHub/Open Source** (`core-projects`), incluindo portfólio.
9. **Sistema de Educação Formal** (`core-education`).
10. **Sistema de Eventos, Oportunidades e Crises** (`core-events`), agora com sistemas suficientes para gerar eventos ricos e interconectados.
11. **Sistema de Networking, NPCs, Comunidades e Mentoria** (`core-networking`).
12. **Sistema de Freelancing e Consultoria** (`core-freelance`).
13. **Sistema de Conteúdo** (`core-content`).
14. **Sistema de Pesquisa Acadêmica** (`core-research`).
15. **Sistema de Liderança e Gestão** (`core-leadership`).
16. **Sistema de Empreendedorismo e Startups** (`core-startup`), por depender de maturidade prévia de finanças, carreira, liderança e projetos.
17. **Sistema de Achievements, Timeline e Legado** (`core-achievements`), incluindo achievements lendários como NEXT LINUS, agora com todos os sistemas-fonte de dados implementados.
18. **Persistência avançada completa:** autosave, backup, export/import, versionamento e migração de saves, exercitando o modelo de dados já consolidado de todos os sistemas anteriores.
19. **UI/UX mobile completa** sobre a API estabilizada, incluindo painel de estado, alocação de tempo, feed de eventos, timeline navegável e telas de perfil detalhadas.
20. **Ciclo de balanceamento contínuo:** ferramentas internas de simulação em lote, ajuste iterativo de curvas de dados, expansão contínua de catálogos (novas tecnologias, cargos, eventos, achievements) como processo permanente do projeto, não como fase final única.

Esta ordem é recomendada para sequenciamento de esforço de desenvolvimento e não representa versões reduzidas dos sistemas: cada sistema, ao ser implementado em sua fase, deve seguir integralmente as regras, dados e interações descritas na Seção 3, sem simplificações de escopo.