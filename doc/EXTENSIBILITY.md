[Voltar para o índice](SPEC.md)



---

# Extensibilidade

- **Tudo que for conteúdo (não regra estrutural) deve ser data-driven:** tecnologias, cargos, empresas-modelo, eventos, achievements, tipos de projeto, formatos de conteúdo, linhas de pesquisa, arquétipos de NPC, e definições de balanceamento devem residir em arquivos/registros de configuração carregados pela camada `platform-config`, permitindo que novo conteúdo seja adicionado sem alterar o núcleo de domínio.
- **Novas áreas técnicas e trilhas de carreira** devem poder ser adicionadas como novos conjuntos de dados (novos nós de skill tree, novos cargos com requisitos próprios) sem exigir novo código de domínio, desde que se encaixem nos conceitos genéricos já modelados (habilidade, cargo, requisito composto).
- **Novos tipos de evento** devem poder ser adicionados via definição declarativa de condição de elegibilidade e efeito, reaproveitando o motor genérico de geração procedural (Seção 10), evitando a necessidade de um novo "case" de código para cada evento futuro sempre que o padrão se encaixar no modelo existente.
- **Novos achievements**, incluindo lendários futuros além de NEXT LINUS, devem poder ser definidos declarativamente como expressões sobre o estado histórico do jogador (semelhante a critérios de query sobre a timeline e sistemas), sem exigir código dedicado por achievement sempre que os critérios se encaixem no vocabulário de condições já suportado pelo motor de achievements.
- **Modularidade da arquitetura (Seção 7.2)** deve permitir que sistemas inteiramente novos (ex.: uma futura expansão de "vida em comunidade offline", "imigração para outro país simulado", "meta-carreira em educação corporativa") sejam adicionados como novos módulos de domínio, integrando-se aos módulos existentes via eventos de domínio e interfaces já estabelecidas, minimizando acoplamento direto.
- **Internacionalização e localização de conteúdo textual** (nomes de empresas, descrições de eventos, textos de achievement) devem ser tratadas como dados separados da lógica, para permitir tradução/expansão regional futura sem tocar em regras de negócio.

---