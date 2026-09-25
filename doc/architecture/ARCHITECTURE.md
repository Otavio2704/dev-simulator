[Voltar para o índice](../SPEC.md)



---

# Arquitetura Técnica

## Visão geral

O jogo é **multiplataforma**: jogável em PC, celular e tablet, distribuído como **versão web** (navegador) e **versão mobile empacotada em APK**, esta última obrigatoriamente capaz de rodar **offline**. Essa exigência molda a arquitetura desde a raiz: o núcleo de domínio (as regras de simulação) precisa ser inteiramente independente de como o estado chega até o jogador ou de onde ele é armazenado, para que o mesmo núcleo sirva tanto a um backend web quanto a um empacotamento offline no dispositivo.

Arquitetura em camadas, com fronteiras estritas de dependência:

```
Presentation → Application → Domain → Infrastructure
```

- **Domain** não depende de nenhuma outra camada nem de frameworks (Spring, banco de dados, etc.) sempre que tecnicamente viável. Contém entidades, agregados, value objects, regras de negócio (motores de simulação de cada sistema descrito na Seção 3) e interfaces (ports) para o que precisa ser implementado externamente (ex.: persistência, geração de números aleatórios determinística, relógio de jogo). Por não depender de nada externo, o mesmo Domain roda igual em servidor (web) ou embarcado no dispositivo (APK offline).
- **Application** orquestra casos de uso (ex.: "AvançarTempo", "IniciarProjeto", "CandidatarSeAVaga", "RealizarEtapaDeEntrevista"), coordenando múltiplos agregados de domínio e chamando ports de infraestrutura via interfaces. Não contém regra de negócio de simulação, apenas orquestração e transação.
- **Infrastructure** implementa os ports definidos no domínio: persistência (com implementações diferentes por plataforma, ver `PERSISTENCE.md`: Spring Data + PostgreSQL para o backend de referência/web, e um motor local embarcado para o APK offline e para o modo offline da versão web), geração procedural (implementações concretas de geradores, podendo usar seed determinística para reprodutibilidade), leitura de configuração data-driven (arquivos de definição de tecnologias, cargos, empresas, eventos, achievements), integrações técnicas (ex.: serialização para export/import de save).
- **Presentation** expõe a API para os clientes (web e mobile) via Spring WebFlux, reativo, adequado a operações potencialmente concorrentes como avanço de tempo com múltiplos efeitos colaterais assíncronos, usando contratos documentados via OpenAPI. Também é responsável por mapear DTOs de entrada/saída, nunca expondo entidades de domínio diretamente. Para o empacotamento em APK offline, essa mesma API (ou um subconjunto equivalente de casos de uso da camada Application) roda embarcada localmente no dispositivo, sem exigir rede.

## Módulos sugeridos

Organização modular por **bounded context**, alinhada aos sistemas da Seção 3, cada um podendo ser um módulo Maven (multi-módulo) ou pacote fortemente isolado, conforme necessidade de build:

- `core-time` (GameClock, avanço de tempo, orquestração de ciclos)
- `core-skills` (conhecimento/habilidades)
- `core-experience` (experiência)
- `core-reputation` (reputação multidimensional)
- `core-education` (educação formal)
- `core-projects` (projetos pessoais e Open Source/GitHub)
- `core-career` (empresas, empregos, entrevistas)
- `core-freelance` (freelancing e consultoria)
- `core-networking` (NPCs, relacionamentos, comunidades, mentoria)
- `core-content` (artigos, vídeos, palestras)
- `core-research` (pesquisa acadêmica)
- `core-startup` (empreendedorismo)
- `core-leadership` (liderança e gestão)
- `core-finance` (sistema financeiro)
- `core-personal-life` (saúde, energia, estresse, satisfação, vida pessoal)
- `core-market` (mercado de tecnologia)
- `core-events` (eventos, oportunidades, crises, geração procedural)
- `core-achievements` (achievements, timeline, legado)
- `platform-persistence` (implementações de persistência: Spring Data/PostgreSQL para backend web de referência, e motor local embarcado para APK offline/modo offline web — ambos implementando os mesmos ports de domínio, ver `PERSISTENCE.md`)
- `platform-config` (carregamento de definições data-driven)
- `api` (camada Presentation, controllers WebFlux, DTOs, OpenAPI)

Cada módulo de domínio expõe casos de uso via Application Services e depende apenas de abstrações (ports), nunca de implementações concretas de outros módulos de infraestrutura.

## Padrões e práticas

- **Domain-Driven Design tático:** Agregados com raízes bem definidas (Player, SaveGame, Startup, Company são candidatos naturais a raízes de agregado), Value Objects para conceitos imutáveis (ex.: faixa salarial, nível de habilidade, período de tempo), Domain Events para comunicar mudanças relevantes entre módulos (ex.: `ProjetoPublicadoEvent`, `EmpregoIniciadoEvent`, `AchievementDesbloqueadoEvent`) sem acoplamento direto.
- **Motores de simulação como Domain Services:** cada sistema da Seção 3 tem um ou mais Domain Services responsáveis por calcular progressão, aplicando regras puras (funções determinísticas dado o estado + parâmetros de tempo/ação), facilitando testes unitários extensivos.
- **Geração procedural determinística:** todo gerador procedural (eventos, NPCs, tecnologias, empresas) deve aceitar uma seed, permitindo reprodutibilidade em testes e, opcionalmente, replays.
- **Programação reativa (WebFlux) na borda:** operações potencialmente custosas (avanço de tempo processando múltiplos sistemas) devem ser modeladas de forma que possam ser paralelizadas/compostas reativamente na camada de Application/Presentation, mesmo que o núcleo de domínio seja síncrono e determinístico internamente.
- **Spring Security preparado para expansão:** ainda que o jogo seja offline single-player, a API deve estruturar autenticação/autorização básica (ex.: proteção local por PIN/senha de perfil, preparação para eventual sincronização em nuvem ou múltiplos perfis na mesma instalação), sem implementar funcionalidades online completas nesta fase.
- **Qualidade contínua:** SonarQube integrado ao pipeline de CI (GitHub Actions) para métricas de cobertura, duplicação, complexidade e vulnerabilidades; quality gates bloqueando merge abaixo de limiares definidos pela equipe.
- **Containerização:** Docker Compose orquestrando a aplicação Spring Boot e o PostgreSQL para ambiente de desenvolvimento/teste local e para a distribuição web com backend.
- **Distribuição multiplataforma:** a mesma base de domínio/aplicação deve poder ser (a) servida como backend web tradicional (Spring Boot + PostgreSQL, atrás de um frontend web responsivo) e (b) empacotada como aplicativo mobile offline (APK), com o motor de persistência local substituindo o backend/PostgreSQL nessa forma de distribuição, conforme detalhado em `PERSISTENCE.md`. A escolha da ferramenta concreta de empacotamento do APK (ex.: wrapper que roda o backend Java localmente no dispositivo, ou reimplementação do client consumindo o domínio compilado para outra plataforma) é uma decisão técnica a ser tomada na fase de implementação correspondente do `ROADMAP.md`, mas não pode comprometer a exigência de funcionamento 100% offline.

---