# Feltrim Agents Base

Boilerplate canonico do **Feltrim Agents Framework (FF)**, criacao original
de Rafael Feltrim. Este repositorio e a fundacao publica da Feltrim Agents
Company: orquestracao multi-agente, governanca, protocolos, rituais e
sistema de niveis/certificacoes para agentes de IA especializados.

> **Foco:** servir de boilerplate para qualquer empresa, time ou solo
> developer que queira operar agentes de IA com disciplina (niveis,
> certificacoes, unlocks), squads hiper-especializados, rituais
> simbolicos auditaveis e respeito ao decisor humano.

## Mapa do repo

```
feltrim-agents-base/
|-- README.md                  # este arquivo
|-- CLAUDE.md                  # boot sequence generico para Claude Code
|-- AGENTS.md                  # espelho do CLAUDE.md para outras CLIs/IDEs
|-- LICENSE                    # licenca proprietaria provisoria
|-- .env.example
|-- .gitignore
|-- DECISIONS_PENDING.md       # itens em aberto para revisao
|
|-- core/                      # GENERICO, reutilizavel por qualquer empresa
|   |-- agents/                # 15 gens canonicas sanitizadas + _template/
|   |-- protocols/             # 8 protocolos (IO, orchestration, handoff, memory, evals, delivery, runtime, multimodal)
|   |-- docs/                  # arquitetura, onboarding, squad index, manifesto, niveis, certificacoes, unlocks, activation policy, token economy
|   |-- memory/                # MEMORY.md indice + templates + agents/ + team-rituals/
|   |-- skills/                # esqueleto para skills de workflow
|   |-- integrations/          # contratos genericos
|   `-- scripts/               # bootstrap.sh, spawn-agent.sh
|
|-- packs/                     # ESPECIFICOS por projeto / dominio (opt-in)
|   |-- _template-pack/        # esqueleto para novos packs
|   |-- cms-gherkin/           # pack BDD/Gherkin com prompts por modelo + ferramentas
|   `-- us-avaliator/          # pack didatico (exemplo de proposta sanitizada)
|
|-- governance/                # GOVERNANCA da empresa Feltrim Agents
|   |-- COMPANY_CHARTER.md
|   |-- AGENT_HIERARCHY.md
|   |-- RITUALS_GUARDRAILS.md
|   |-- PROMOTION_POLICY.md
|   |-- CERTIFICATION_POLICY.md
|   `-- SECURITY_AND_PRIVACY.md
|
|-- examples/                  # exemplos de uso
`-- .specify/                  # opcional: Spec Kit constitution generica
```

## Como navegar

- **Quer entender o framework?** Comece em `core/docs/manifesto/FELTRIMS_FRAMEWORK_MANIFESTO.md`.
- **Quer rodar agentes?** Leia `CLAUDE.md` (boot sequence) + `core/docs/SQUAD_INDEX.md` (roster + triggers).
- **Preocupado com custo de token?** Leia `core/docs/AGENT_ACTIVATION_POLICY.md` e `core/docs/TOKEN_ECONOMY.md`.
- **Quer criar um novo pack?** Copie `packs/_template-pack/` e siga `examples/example-pack-init.md`.
- **Trabalhando em CMS / Gherkin BDD?** Use `packs/cms-gherkin/`.
- **Avaliando Studio de QA / substituicao Copilot?** Use `packs/us-avaliator/`.
- **Quer entender governanca da empresa?** Leia tudo em `governance/`.

## Conceitos centrais

| Conceito | O que e | Onde |
|----------|---------|------|
| Squad de 15 gens | Personas canonicas (CIAO, TL, PO, PM, devs, design, QA, etc.) | `core/agents/` |
| 8 protocolos | Contratos universais de IO, handoff, memory, evals | `core/protocols/` |
| 4 modos de ativacao | SOLO / PAR / MINI / FULL - escolha por escopo | `core/docs/AGENT_ACTIVATION_POLICY.md` |
| Sistema de niveis | N1-N5 com criterios auditaveis | `core/docs/AGENT_LEVELS_AND_CERTIFICATIONS.md` |
| Certificacoes internas | Reconhecem competencias com evidencia | `core/docs/AGENT_CERTIFICATIONS.md` |
| Unlocks | Habilidades operacionais desbloqueadas | `core/docs/AGENT_UNLOCKS.md` |
| Memoria operacional | brain.md por agente + rituais de equipe | `core/memory/` |
| Cultura simbolica | XP, rituais, escala temporal - nao substituem metricas | `governance/RITUALS_GUARDRAILS.md` |
| Chat -> Artefato | Toda decisao tecnica vira ADR/runbook | `core/docs/CHAT_TO_ARTIFACT_GOVERNANCE.md` |

## Estado atual

Boilerplate MVP **completo e publico**:

- **core/** (15 gens + 8 protocolos + 11 rituais + 13 docs + memoria
  generica).
- **governance/** (6 docs de governanca da empresa).
- **packs/** publicos (2 packs ativos: `cms-gherkin`, `us-avaliator` +
  `_template-pack`).
- **examples/** (3 exemplos: spawn team meeting, feature lean,
  benchmark de modelo).
- **.specify/memory/constitution.md** (Spec Kit generico).

## O que NAO esta neste repositorio

- Packs especificos de cliente (vivem em repositorio privado por
  exigencia contratual / IP).
- Snapshots historicos de versoes anteriores do framework (privado).
- Listas de palavras-bandeira reais com nomes de clientes (cada
  instalacao mantem a sua, fora do `core/`).

## Origem

Este repositorio consolida varias iteracoes do Feltrim Agents Framework
(FF v1 -> v2 -> v3) em um boilerplate canonico publico, criado por
Rafael Feltrim em Maio/2026.

## Licenca

Ver `LICENSE` (proprietaria provisoria). Decisao de licenca final
pendente - ver `DECISIONS_PENDING.md`.

## Proximos passos sugeridos

1. Revisar `DECISIONS_PENDING.md` (itens em aberto para revisao humana).
2. Atualizar prompts das gens com metadados de nivel/cert para sua
   instalacao (campos `Nivel atual:`, `Certificacoes:`, `Unlocks:` no
   header da gem - ver `core/agents/_template/gem-skeleton.md`).
3. Inicializar `core/memory/agents/<slug>/agent-profile.md` para cada
   agente em uso (template em
   `core/memory/agents/_templates/agent-profile-template.md`).
4. Configurar pre-commit hook com a busca de palavras-bandeira da sua
   instalacao (ver `governance/SECURITY_AND_PRIVACY.md`).
5. Criar packs proprios em repositorio privado para projetos com IP de
   cliente.
