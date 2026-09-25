# Checklist de migração — SPEC.md original → múltiplos arquivos

Conferência de que todo o conteúdo do `SPEC.md` original foi preservado na nova estrutura, sem cortes.

| Seção original | Conteúdo | Arquivo de destino | Status |
|---|---|---|---|
| 1 | Visão e Princípios do Jogo | `docs/SPEC.md` | ✅ |
| 2 | Loop Principal | `docs/SPEC.md` | ✅ |
| 3.1 | Conhecimento e Habilidades | `docs/systems/SKILLS.md` | ✅ |
| 3.2 | Educação Formal | `docs/systems/EDUCATION.md` | ✅ |
| 3.3 | Projetos Pessoais | `docs/systems/PROJECTS.md` | ✅ |
| 3.4 | GitHub e Open Source | `docs/systems/PROJECTS.md` | ✅ |
| 3.5 | Carreira, Empresas e Empregos | `docs/systems/CAREER.md` | ✅ |
| 3.6 | Freelancing e Consultoria | `docs/systems/FREELANCE.md` | ✅ |
| 3.7 | Networking, NPCs, Comunidades e Mentoria | `docs/systems/NETWORKING.md` | ✅ |
| 3.8 | Conteúdo | `docs/systems/CONTENT.md` | ✅ |
| 3.9 | Pesquisa Acadêmica | `docs/systems/RESEARCH.md` | ✅ |
| 3.10 | Empreendedorismo e Startups | `docs/systems/STARTUP.md` | ✅ |
| 3.11 | Liderança e Gestão | `docs/systems/LEADERSHIP.md` | ✅ |
| 3.12 | Reputação Multidimensional | `docs/systems/REPUTATION.md` | ✅ |
| 3.13 | Conhecimento vs. Experiência vs. Reputação | `docs/systems/SKILLS.md` | ✅ |
| 3.14 | Sistema Financeiro | `docs/systems/FINANCE.md` | ✅ |
| 3.15 | Vida Pessoal | `docs/systems/PERSONAL_LIFE.md` | ✅ |
| 3.16 | Mercado de Tecnologia | `docs/systems/MARKET.md` | ✅ |
| 3.17 | Eventos, Oportunidades e Crises (referência) | `docs/systems/EVENTS.md` | ✅ |
| 3.18 | Achievements, Timeline e Legado | `docs/systems/ACHIEVEMENTS.md` | ✅ |
| 4 | Entidades e Relacionamentos | `docs/DOMAIN_MODEL.md` | ✅ |
| 5 | Regras de Progressão | `docs/PROGRESSION_RULES.md` | ✅ |
| 6 | Interação entre Sistemas | `docs/PROGRESSION_RULES.md` | ✅ |
| 7 | Arquitetura Técnica | `docs/architecture/ARCHITECTURE.md` | ✅ |
| 8 | Persistência | `docs/architecture/PERSISTENCE.md` | ✅ |
| 9 | UI/UX Mobile | `docs/UX.md` | ✅ |
| 10 | Eventos e Geração Procedural (completo, 10.1–10.4) | `docs/systems/EVENTS.md` | ✅ |
| 11 | Balanceamento | `docs/BALANCING.md` | ✅ |
| 12 | Testes | `docs/TESTING.md` | ✅ |
| 13 | Extensibilidade | `docs/EXTENSIBILITY.md` | ✅ |
| 14 | Ordem Recomendada de Implementação | `docs/ROADMAP.md` | ✅ |

## Observações

- Nenhuma frase do conteúdo técnico original foi resumida, cortada ou reescrita. Cada arquivo derivado contém a subseção correspondente na íntegra, apenas com o nível de heading ajustado para ficar autocontido.
- O arquivo `docs/SPEC.md` agora é enxuto (contém só Visão, Loop Principal e o índice); todo o restante do conteúdo técnico foi movido para os arquivos especializados listados acima, nunca duplicado nem perdido.
- Cada arquivo em `docs/systems/` recebeu um cabeçalho com link de volta ao índice e uma lista de "Sistemas relacionados", além de um rodapé de "Referências cruzadas" — esse conteúdo é adicional e não substitui nada do original.
- `docs/DOMAIN_MODEL.md` recebeu, ao final, uma nota indicando em qual arquivo de sistema cada entidade é aprofundada — também aditivo, sem remoção do conteúdo original de entidades e relacionamentos.
- Total de arquivos gerados: 1 (`SPEC.md`) + 2 (`architecture/`) + 16 (`systems/`) + 6 (`DOMAIN_MODEL.md`, `PROGRESSION_RULES.md`, `UX.md`, `BALANCING.md`, `TESTING.md`, `EXTENSIBILITY.md`) + 1 (`ROADMAP.md`) = 26 arquivos.

## Atualizações pós-migração

| Data/contexto | Mudança | Arquivos afetados |
|---|---|---|
| Definição de escopo multiplataforma | Jogo passou de "mobile offline" para multiplataforma (PC, celular, tablet), distribuído como web + APK mobile offline. Regras de save agora incluem 3 slots manuais + autosave, com opção de excluir save de slot. | `SPEC.md`, `architecture/ARCHITECTURE.md`, `architecture/PERSISTENCE.md`, `UX.md` |

Nenhuma regra de negócio dos sistemas (`systems/*.md`), do modelo de domínio (`DOMAIN_MODEL.md`) ou das regras de progressão (`PROGRESSION_RULES.md`) foi alterada por essa atualização; o impacto ficou restrito a arquitetura, persistência e UX.
