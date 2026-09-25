[Voltar para o índice](SPEC.md)



---

# Balanceamento

- **Curvas de progressão calibráveis externamente:** toda curva de custo/recompensa (XP necessário por nível de habilidade, tempo necessário por etapa educacional, probabilidade de sucesso em entrevista, taxa de crescimento de reputação) deve ser definida em dados de configuração, nunca hardcoded, para permitir ajuste iterativo sem alteração do núcleo de domínio.
- **Múltiplos caminhos devem ser viáveis, não apenas possíveis:** balanceamento deve ser testado explicitamente para garantir que trajetórias alternativas (ex.: foco em Open Source puro vs. carreira corporativa tradicional vs. empreendedorismo) sejam todas jogáveis até os patamares mais altos, ainda que com desafios e ritmos diferentes.
- **Trade-offs de tempo devem ser sempre sensíveis:** nenhuma alocação de tempo deve ser estritamente dominante sobre as demais em todos os cenários; o valor relativo de estudar vs. trabalhar vs. socializar deve variar conforme fase de carreira e objetivos do jogador.
- **Raridade calibrada de achievements lendários:** achievements como NEXT LINUS devem ser calibrados via simulação/playtesting para serem extremamente raros mesmo em jogo otimizado (mas não matematicamente impossíveis), preservando seu significado de marco excepcional.
- **Prevenção de estratégias degeneradas:** balanceamento deve considerar e mitigar loops de "vitória garantida" triviais (ex.: acumular dinheiro infinito sem risco, ou subir reputação sem nenhum custo de tempo/energia).
- **Ferramentas internas de balanceamento:** recomenda-se a construção de utilitários internos (fora do escopo de código de produção deste SPEC, mas a prever na arquitetura) para simular partidas automatizadas em lote e analisar curvas resultantes de progressão, tempo médio para marcos-chave e distribuição de trajetórias.

---