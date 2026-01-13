# Canonical Material - Melhorias na Estrutura de Pastas por Roles

**Versão:** v1.0
**Aprovado em:** 2026-01-13
**Aprovador:** [A ser preenchido]
**Referência Filtered Material:** `filter/1_filtered_estrutura_pastas.md`
**Role:** Análise

---

## Status

✅ **Aprovado como Canonical Material**

Este material foi revisado, ajustado e aprovado como fonte oficial de verdade para as próximas etapas.

---

## Conteúdo Validado

### 0. Três Pilares Fundamentais do Canonical Cycle

Identificados e aprovados, três pilares que sustentam o funcionamento do Canonical Cycle:

#### Pilar 1: Bancada de Trabalho (Workspace Agent)
- **Função:** Dando contexto para a code base e entendimento do produto
- **Responsabilidade:** Fornecer ao agente acesso e compreensão do workspace/codebase
- **Aplicação:** Agentes precisam entender o código, estrutura do projeto, contexto técnico
- **Integração:** Deve estar disponível para agentes durante todo o processo do Canonical Cycle

#### Pilar 2: Fluxo de Trabalho/Regras de Artefatos/Personas/Skills (Canonical Cycle Agent)
- **Função:** Definir e executar o fluxo de trabalho, regras de artefatos, personas e skills
- **Responsabilidade:** Gerenciar o Canonical Cycle, aplicar regras, seguir personas e usar skills específicas
- **Aplicação:** Agentes seguem o fluxo Raw → Filtered → Canonical → Artifacts com regras específicas por role
- **Integração:** Define o comportamento e fluxo dos agentes em cada etapa

#### Pilar 3: Contextos Abertos/Externos (MCPs)
- **Função:** Pegar dados e conhecimentos de fontes externas
- **Responsabilidade:** Acessar sistemas externos (Jira, Confluence, etc.) e conhecimentos que não estão no workspace
- **Aplicação:** Durante o fluxo de trabalho, agentes podem precisar buscar dados no Jira, conhecimentos sobre funcionamento da empresa/produtos, informações que não estão no workspace
- **Integração:** Disponível quando agentes precisam de informações externas durante o processo

**Exemplo prático:** No meio do fluxo de trabalho, o agente precisa pegar dados no Jira ou conhecimentos de funcionamento da empresa de produtos que não estão no workspace.

**Aplicação ao Canonical Cycle:**
- Esses três pilares devem estar disponíveis para os agentes durante todo o processo
- Agentes devem ter acesso a workspace, seguir regras do ciclo, e buscar informações externas quando necessário
- Documentação deve explicar como cada pilar se integra ao fluxo
- Cada pilar é essencial e complementa os outros

---

### 1. Nova Estrutura de Pastas Aprovada

#### 1.1 Estrutura Atual (a ser substituída)

**Estrutura atual do Canonical Cycle:**
```
archives/
└── numeracao_nome_ciclo/
    ├── raw/
    ├── filter/
    ├── canonical/
    └── artifacts/
```

**Características:**
- Todas as roles compartilham as mesmas pastas
- Não há separação clara por role
- Pode ser confuso identificar qual role gerou qual arquivo

#### 1.2 Nova Estrutura Aprovada

**Nova estrutura do Canonical Cycle:**
```
archives/
└── numeracao_nome_ciclo/
    ├── analista/
    │   ├── raw/
    │   ├── filter/
    │   ├── canonical/
    │   └── artifacts/
    ├── designer/ (quando necessário)
    │   ├── raw/
    │   ├── filter/
    │   ├── canonical/
    │   └── artifacts/
    ├── arquiteto/ (quando necessário)
    │   ├── raw/
    │   ├── filter/
    │   ├── canonical/
    │   └── artifacts/
    ├── engenheiro/
    │   ├── raw/
    │   ├── filter/
    │   ├── canonical/
    │   └── artifacts/
    └── desenvolvedor/
        ├── raw/
        ├── filter/
        ├── canonical/
        └── artifacts/
```

**Características Aprovadas:**
- Cada role tem suas próprias pastas
- Separação clara por responsabilidade
- Melhor rastreabilidade por role
- Roles opcionais podem não ter pasta (ou ter pasta vazia)
- Cada role mantém seu próprio ciclo interno (raw → filter → canonical → artifacts)

---

### 2. Benefícios da Nova Estrutura

#### 2.1 Organização
- **Separação clara:** Cada role tem seu próprio espaço
- **Rastreabilidade:** Fácil identificar qual role gerou qual artefato
- **Escalabilidade:** Fácil adicionar novas roles no futuro

#### 2.2 Manutenção
- **Isolamento:** Mudanças em uma role não afetam outras
- **Navegação:** Mais fácil encontrar arquivos de uma role específica
- **Histórico:** Histórico por role fica mais claro

#### 2.3 Fluxo Sequencial
- **Clareza:** Fica explícito que cada role tem seu próprio ciclo
- **Paralelismo:** Potencial para trabalhar em múltiplas roles (se necessário)
- **Rastreabilidade:** Fácil ver o progresso de cada role no ciclo

---

### 3. Regras de Numeração e Estrutura

#### 3.1 Numeração do Ciclo
- **Nome do ciclo:** Deve começar com numeração indicando ordem de criação
  - Exemplo: `1_inicio_projeto`, `2_primeiras_melhorias`, `3_melhorias_de_fluxo_de_trabalho`

#### 3.2 Pastas de Roles
- **Pastas de roles:** NÃO devem ter numeração
  - ✅ Correto: `analista/`, `designer/`, `arquiteto/`, `engenheiro/`, `desenvolvedor/`
  - ❌ Incorreto: `1_analista/`, `2_designer/`

#### 3.3 Pastas de Etapas
- **Pastas das etapas:** NÃO devem ter numeração
  - ✅ Correto: `raw/`, `filter/`, `canonical/`, `artifacts/`
  - ❌ Incorreto: `1_raw/`, `2_filter/`

#### 3.4 Numeração de Arquivos
- **Arquivos dentro das etapas:** Devem começar com numeração indicando ordem de criação **dentro da role**
  - Exemplo: `analista/raw/1_requisitos.md`, `analista/raw/2_anotacoes.md`
  - Exemplo: `designer/raw/1_prototipo.md` (numeração independente por role)
  - **Regra:** Cada role começa sua numeração do 1

---

### 4. Fluxo Sequencial com Nova Estrutura

**Fluxo por role:**
```
archives/nome_ciclo/
├── analista/
│   ├── raw/ → filter/ → canonical/ → artifacts/
│   └── (artefatos passam para designer/raw/ ou arquiteto/raw/)
├── designer/ (se necessário)
│   ├── raw/ → filter/ → canonical/ → artifacts/
│   └── (artefatos passam para arquiteto/raw/ ou engenheiro/raw/)
├── arquiteto/ (se necessário)
│   ├── raw/ → filter/ → canonical/ → artifacts/
│   └── (artefatos passam para engenheiro/raw/)
├── engenheiro/
│   ├── raw/ → filter/ → canonical/ → artifacts/
│   └── (artefatos passam para desenvolvedor/raw/)
└── desenvolvedor/
    ├── raw/ → filter/ → canonical/ → artifacts/
    └── (commit final)
```

**Observação:** Cada role mantém seu próprio ciclo interno, mas os artefatos de uma role se tornam raw da próxima.

---

## Decisões Tomadas Durante Revisão

### Decisão 1: Como Artefatos Viram Raw da Próxima Role
- **Ambiguidade original:** Não estava claro como artefatos de uma role se tornam raw da próxima
- **Decisão:** Os artefatos de uma role (ex: `analista/artifacts/`) devem ser copiados ou referenciados na pasta `raw/` da próxima role (ex: `designer/raw/`). O agente deve criar um arquivo raw na próxima role referenciando ou copiando o conteúdo dos artefatos da role anterior.
- **Justificativa:** Mantém rastreabilidade e permite que cada role tenha seu próprio ciclo completo, enquanto preserva o fluxo sequencial.

### Decisão 2: Roles Opcionais
- **Ambiguidade original:** Não estava claro como tratar roles opcionais na estrutura
- **Decisão:** Pastas de roles opcionais (Designer, Arquiteto) devem ser criadas apenas quando a role for necessária. Se uma role for pulada, sua pasta não deve ser criada. Isso torna explícito quais roles foram usadas no ciclo.
- **Justificativa:** Evita pastas vazias e deixa claro quais roles participaram do ciclo.

### Decisão 3: Numeração de Arquivos
- **Ambiguidade original:** Não estava claro se numeração é por role ou global
- **Decisão:** Numeração de arquivos é **independente por role**. Cada role começa sua numeração do 1. Exemplo: `analista/raw/1_requisitos.md`, `designer/raw/1_prototipo.md` (ambos podem ter numeração 1).
- **Justificativa:** Cada role tem seu próprio contexto e histórico, então faz sentido ter numeração independente.

### Decisão 4: Compatibilidade com Estrutura Atual
- **Ambiguidade original:** Não estava claro como migrar ou se manter compatibilidade
- **Decisão:** A nova estrutura substitui a estrutura antiga. Ciclos existentes podem ser migrados manualmente se necessário, mas novos ciclos devem usar a nova estrutura. A estrutura antiga pode coexistir temporariamente durante período de transição.
- **Justificativa:** Nova estrutura é melhor e deve ser adotada, mas transição pode ser gradual.

### Decisão 5: Comportamento do Agente
- **Ambiguidade original:** Não estava claro como o agente deve se comportar com a nova estrutura
- **Decisão:** O agente deve identificar tanto o ciclo quanto a role atual. Deve criar arquivos na pasta correta da role dentro do ciclo. O agente identifica a role pelo contexto do prompt ou pela localização do arquivo raw que está processando.
- **Justificativa:** Agente precisa saber onde criar arquivos e manter organização correta.

### Decisão 6: Integração dos Três Pilares
- **Ambiguidade original:** Como os três pilares (Workspace Agent, Canonical Cycle Agent, MCPs) se integram ao fluxo
- **Decisão:** Os três pilares são fundamentais e devem estar documentados e disponíveis para agentes. Cada pilar tem sua função específica e complementa os outros. A documentação deve explicar como agentes acessam e usam cada pilar durante o processo.
- **Justificativa:** Os três pilares são a base do sistema e precisam estar claramente definidos e integrados ao fluxo de trabalho.

---

## Suposições Validadas

1. ✅ **Estrutura deve ser separada por role** - validado, melhora organização e rastreabilidade
2. ✅ **Cada role mantém seu próprio ciclo** - validado, raw → filter → canonical → artifacts dentro de cada role
3. ✅ **Fluxo sequencial é mantido** - validado, artefatos de uma role alimentam a próxima
4. ✅ **Numeração continua no nome do ciclo** - validado, mantém padrão atual
5. ✅ **Pastas das etapas não têm numeração** - validado, mantém padrão atual
6. ✅ **Roles opcionais não têm pasta quando não usadas** - validado, evita pastas vazias
7. ✅ **Três pilares fundamentais** - Workspace Agent, Canonical Cycle Agent, e MCPs são base do sistema
8. ✅ **Agentes precisam acesso a múltiplos contextos** - workspace, regras do ciclo, e fontes externas

---

## Correções Realizadas

- Estrutura de pastas por role aprovada como padrão
- Regras de numeração definidas (independente por role)
- Processo de transição de artefatos entre roles definido
- Comportamento do agente documentado
- Três pilares fundamentais identificados e aprovados

---

## Histórico de Versões

| Versão | Data | Aprovador | Mudanças |
|--------|------|-----------|----------|
| v1.0 | 2026-01-13 | [A ser preenchido] | Versão inicial aprovada |
| v1.1 | 2026-01-13 | [A ser preenchido] | Adicionados três pilares fundamentais |

---

## Pronto para Geração de Artefatos

✅ Este Canonical Material está pronto para ser usado como fonte para geração de artefatos.

**Artefatos sugeridos:**
- Atualização do README.md com nova estrutura de pastas e três pilares fundamentais
- Atualização do AGENTS.md com comportamento do agente na nova estrutura e acesso aos três pilares
- Atualização do GUIDELINES.md com diretrizes para nova estrutura
- Documentação dos três pilares fundamentais (seção dedicada ou integrada)
- Criação de guia de migração (se necessário)
- Atualização de templates com novos caminhos
- Exemplo prático da nova estrutura

**Regra:** Qualquer alteração relevante neste material requer novo Canonical Cycle.

---

**Nota:** Este é material canônico - fonte única de verdade. Não será reinterpretado sem novo ciclo.
