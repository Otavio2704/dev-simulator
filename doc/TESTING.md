[Voltar para o índice](SPEC.md)



---

# Testes

- **Testes unitários (JUnit 5 + Mockito)** extensivos sobre os Domain Services de cada sistema (Seção 3), validando regras de progressão, requisitos de elegibilidade, cálculos de decaimento e efeitos de eventos de forma isolada, sem depender de infraestrutura real.
- **Testes de geração procedural determinística:** para cada gerador (eventos, NPCs, tecnologias, empresas), testes garantindo que a mesma seed + mesmo estado produzem sempre o mesmo resultado.
- **Testes de integração** cobrindo casos de uso completos da camada Application (ex.: fluxo completo de candidatura a emprego até contratação ou rejeição), incluindo persistência real contra PostgreSQL (via containers de teste).
- **Testes de persistência dedicados:** save/load, autosave, export/import, e especialmente **migração de versões de save**, com fixtures representando saves de versões antigas para garantir migração correta ao longo da evolução do jogo.
- **Testes de simulação de longo prazo ("fast-forward tests"):** cenários que avançam o tempo simulado por anos/décadas em lote, verificando ausência de estados inválidos, ausência de degradação de performance e plausibilidade estatística dos resultados agregados (ex.: distribuição de reputação/patrimônio ao final de N anos simulados dentro de faixas esperadas).
- **Testes de contrato de API (OpenAPI):** garantindo que a documentação da API reflita fielmente o comportamento real dos endpoints expostos pela camada Presentation.
- **Cobertura e qualidade monitoradas via SonarQube**, integradas ao pipeline de CI (GitHub Actions), com quality gates definidos pela equipe antes de qualquer merge.

---