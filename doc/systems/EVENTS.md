# Sistema: Eventos, Oportunidades e Crises

[Voltar para o índice](../SPEC.md)

## Sistemas relacionados

- [MARKET](./MARKET.md)
- [CAREER](./CAREER.md)
- [FINANCE](./FINANCE.md)
- [PERSONAL_LIFE](./PERSONAL_LIFE.md)
- [NETWORKING](./NETWORKING.md)

---

# Sistema de Eventos, Oportunidades e Crises

Ver detalhamento completo na Seção 10 (Eventos e Geração Procedural).

---

---

# Eventos e Geração Procedural

## Objetivo

Garantir que o mundo simulado nunca seja estático nem puramente reativo às ações do jogador, introduzindo variabilidade, surpresa e consequência de longo prazo através de eventos gerados de forma procedural.

## Categorias de eventos

- **Oportunidades:** vagas de emprego, convites de palestra/artigo, propostas de freelance, convites de colaboração em projeto Open Source, convites de mentoria (como mentor ou mentorado), oportunidades de investimento, convites para cofundar startup, editais de pesquisa/bolsas.
- **Crises:** demissão em massa na empresa atual, falência de cliente freelance, crise pessoal de saúde, conflito em equipe/startup, obsolescência acelerada de uma tecnologia dominante do jogador, crise econômica de mercado, escândalo/erro técnico grave com impacto reputacional.
- **Eventos neutros/narrativos:** mudança de liderança em empresa onde o jogador trabalha, NPC relevante muda de carreira ou de vida, tecnologia nova surge no mercado, evento de comunidade acontece na região do jogador, marco pessoal (aniversário de carreira, marco de idade).
- **Eventos de vida pessoal:** namoro, casamento, filhos, problemas familiares, mudança de cidade/país (simulada).

## Regras de geração

- Cada evento potencial tem uma **condição de elegibilidade** (baseada no estado atual do jogador: cargo, reputação, patrimônio, relacionamentos, saúde) e um **peso de probabilidade** que pode ser modulado por esse mesmo estado e pelo estado do mundo (mercado, economia simulada).
- Geração ocorre nos pontos de avanço de tempo (Seção 2.3), com frequência e intensidade variando por escala (eventos diários são pequenos/frequentes; eventos anuais/decenais são raros/grandes).
- Todo evento gerado deve ser **determinístico dada uma seed e o estado no momento da geração**, permitindo testes reproduzíveis e, potencialmente, funcionalidades futuras de replay/depuração.
- Eventos podem exigir **resposta do jogador** (aceitar/recusar/negociar) ou serem **automáticos/informativos** (o mundo simplesmente muda e o jogador é notificado).
- Cadeias de eventos são permitidas: um evento pode desbloquear ou aumentar a probabilidade de outros eventos relacionados no futuro (ex.: aceitar uma oportunidade de investimento em ações aumenta a chance de eventos futuros ligados a mercado financeiro).

## Dados necessários

- Catálogo de definições de evento (tipo, condições de elegibilidade expressas de forma avaliável sobre o estado do jogador/mundo, peso base, efeitos possíveis, opções de resposta quando aplicável).
- Parâmetros globais de frequência de geração por escala de tempo, ajustáveis para balanceamento.

---

---

## Referências cruzadas

- Modelo de entidades relevantes: [DOMAIN_MODEL.md](../DOMAIN_MODEL.md)
- Regras de progressão e interação entre sistemas: [PROGRESSION_RULES.md](../PROGRESSION_RULES.md)
- Arquitetura e módulo correspondente: [architecture/ARCHITECTURE.md](../architecture/ARCHITECTURE.md)
- Ordem de implementação: [ROADMAP.md](../ROADMAP.md)
