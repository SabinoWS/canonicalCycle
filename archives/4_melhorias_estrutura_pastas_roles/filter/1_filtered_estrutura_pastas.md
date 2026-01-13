# Filtered Material - Melhorias na Estrutura de Pastas por Roles

**Referência Raw Material:** `raw/conversa.txt`, `raw/image.png`
**Gerado em:** 2026-01-13
**Agente:** Agente de Filtragem - Análise
**Role:** Análise

---

## Resumo Executivo

Este material contém duas propostas de melhoria para o Canonical Cycle:

1. **Estrutura de pastas separada por roles:** Organizar as pastas por role ao invés de ter uma estrutura única por ciclo. Cada role teria suas próprias pastas (raw, filter, canonical, artifacts) dentro do ciclo.

2. **Três pilares fundamentais:** Identificação de três pilares que sustentam o Canonical Cycle:
   - Bancada de trabalho (workspace agent) - contexto para code base e entendimento do produto
   - Fluxo de trabalho/regras de artefatos/personas/skills (canonical cycle agent)
   - Contextos abertos/externos (MCPs) - para pegar dados e conhecimentos externos

A estrutura atual agrupa tudo em um único nível (raw, filter, canonical, artifacts), enquanto a proposta sugere separar por role (analista, designer, arquiteto, engenheiro, desenvolvedor), cada uma com suas próprias subpastas.

---

## Informações Estruturadas

### 0. Três Pilares Fundamentais do Canonical Cycle

Identificados na conversa, três pilares que sustentam o funcionamento do Canonical Cycle:

#### Pilar 1: Bancada de Trabalho (Workspace Agent)
- **Função:** Dando contexto para a code base e entendimento do produto
- **Responsabilidade:** Fornecer ao agente acesso e compreensão do workspace/codebase
- **Aplicação:** Agentes precisam entender o código, estrutura do projeto, contexto técnico

#### Pilar 2: Fluxo de Trabalho/Regras de Artefatos/Personas/Skills (Canonical Cycle Agent)
- **Função:** Definir e executar o fluxo de trabalho, regras de artefatos, personas e skills
- **Responsabilidade:** Gerenciar o Canonical Cycle, aplicar regras, seguir personas e usar skills específicas
- **Aplicação:** Agentes seguem o fluxo Raw → Filtered → Canonical → Artifacts com regras específicas por role

#### Pilar 3: Contextos Abertos/Externos (MCPs)
- **Função:** Pegar dados e conhecimentos de fontes externas
- **Responsabilidade:** Acessar sistemas externos (Jira, Confluence, etc.) e conhecimentos que não estão no workspace
- **Aplicação:** Durante o fluxo de trabalho, agentes podem precisar buscar dados no Jira, conhecimentos sobre funcionamento da empresa/produtos, informações que não estão no workspace

**Exemplo prático:** No meio do fluxo de trabalho, o agente precisa pegar dados no Jira ou conhecimentos de funcionamento da empresa de produtos que não estão no workspace.

**Aplicação ao Canonical Cycle:**
- Esses três pilares devem estar disponíveis para os agentes durante todo o processo
- Agentes devem ter acesso a workspace, seguir regras do ciclo, e buscar informações externas quando necessário
- Documentação deve explicar como cada pilar se integra ao fluxo

---

## Informações Estruturadas

### 1. Proposta de Nova Estrutura

#### 1.1 Estrutura Atual

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

#### 1.2 Estrutura Proposta

**Nova estrutura proposta:**
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

**Características:**
- Cada role tem suas próprias pastas
- Separação clara por responsabilidade
- Melhor rastreabilidade por role
- Roles opcionais podem não ter pasta (ou ter pasta vazia)

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

### 3. Impacto no Fluxo

#### 3.1 Fluxo Atual
```
archives/nome_ciclo/
├── raw/ (todos os raws juntos)
├── filter/ (todos os filters juntos)
├── canonical/ (todos os canonicals juntos)
└── artifacts/ (todos os artifacts juntos)
```

#### 3.2 Fluxo Proposto
```
archives/nome_ciclo/
├── analista/
│   ├── raw/ → filter/ → canonical/ → artifacts/
├── designer/ (se necessário)
│   ├── raw/ → filter/ → canonical/ → artifacts/
├── arquiteto/ (se necessário)
│   ├── raw/ → filter/ → canonical/ → artifacts/
├── engenheiro/
│   ├── raw/ → filter/ → canonical/ → artifacts/
└── desenvolvedor/
    ├── raw/ → filter/ → canonical/ → artifacts/
```

**Observação:** Cada role mantém seu próprio ciclo interno, mas os artefatos de uma role se tornam raw da próxima.

---

## Padrões Identificados

1. **Separação por Responsabilidade:** Cada role tem seu próprio espaço
2. **Ciclo Interno por Role:** Cada role mantém seu próprio ciclo (raw → filter → canonical → artifacts)
3. **Fluxo Sequencial Mantido:** Artefatos de uma role viram raw da próxima
4. **Opcionalidade Preservada:** Roles opcionais podem não ter pasta ou ter pasta vazia
5. **Rastreabilidade Melhorada:** Fácil identificar origem e destino de cada artefato

---

## Ambiguidades

> **IMPORTANTE:** Esta seção é obrigatória. Liste todas as ambiguidades encontradas.

### Ambiguidade 1: Como Artefatos Viram Raw da Próxima Role?
- **Descrição:** Na estrutura proposta, cada role tem sua própria pasta `artifacts/`. Não está claro como os artefatos de uma role (ex: analista/artifacts/) se tornam raw da próxima role (ex: designer/raw/). 
  - Os artefatos são copiados?
  - São referenciados?
  - Há uma pasta compartilhada?
- **Contexto:** Fluxo sequencial entre roles
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 2: Roles Opcionais
- **Descrição:** Para roles opcionais (Designer, Arquiteto), não está claro:
  - A pasta deve ser criada mesmo quando não usada?
  - A pasta deve ser criada apenas quando a role for necessária?
  - Como indicar que uma role foi pulada?
- **Contexto:** Roles opcionais na estrutura
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 3: Numeração de Arquivos
- **Descrição:** Com a nova estrutura, a numeração de arquivos deve ser:
  - Por role (ex: analista/raw/1_requisitos.md, designer/raw/1_prototipo.md)?
  - Global no ciclo (ex: analista/raw/1_requisitos.md, designer/raw/2_prototipo.md)?
  - Independente por role (cada role começa do 1)?
- **Contexto:** Regras de numeração de arquivos
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 4: Compatibilidade com Estrutura Atual
- **Descrição:** Não está claro:
  - Como migrar ciclos existentes da estrutura antiga para a nova?
  - Devem coexistir ambas as estruturas?
  - A nova estrutura substitui completamente a antiga?
- **Contexto:** Migração e compatibilidade
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 5: Comportamento do Agente
- **Descrição:** Com a nova estrutura, o agente precisa:
  - Identificar a role atual além do ciclo?
  - Criar arquivos na pasta correta da role?
  - Como identificar qual role está processando?
- **Contexto:** Comportamento do agente de filtragem
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 6: Integração dos Três Pilares
- **Descrição:** Os três pilares identificados (Workspace Agent, Canonical Cycle Agent, MCPs) não estão claramente documentados:
  - Como cada pilar se integra ao fluxo?
  - Quando cada pilar é usado?
  - Como agentes acessam cada pilar?
  - Devem ser documentados no README, AGENTS.md ou em documento separado?
- **Contexto:** Três pilares fundamentais
- **Necessita esclarecimento humano:** SIM

---

## Suposições Explícitas

1. **Estrutura deve ser separada por role** - baseado na proposta explícita
2. **Cada role mantém seu próprio ciclo** - raw → filter → canonical → artifacts dentro de cada role
3. **Fluxo sequencial é mantido** - artefatos de uma role alimentam a próxima
4. **Numeração continua no nome do ciclo** - exemplo mostra "numeracao_nome_ciclo"
5. **Pastas das etapas não têm numeração** - mantém padrão atual (raw/, não 1_raw/)
6. **Roles opcionais podem não ter pasta** - ou ter pasta vazia quando não usadas
7. **Três pilares fundamentais** - Workspace Agent, Canonical Cycle Agent, e MCPs são base do sistema
8. **Agentes precisam acesso a múltiplos contextos** - workspace, regras do ciclo, e fontes externas

---

## Pontos de Atenção

### Riscos Identificados

1. **Risco de Complexidade:** Estrutura mais aninhada pode ser mais complexa de navegar
   - **Mitigação:** Documentação clara e exemplos

2. **Risco de Migração:** Ciclos existentes precisarão ser migrados
   - **Mitigação:** Criar guia de migração ou manter compatibilidade

3. **Risco de Duplicação:** Artefatos podem precisar ser copiados entre roles
   - **Mitigação:** Definir processo claro de como artefatos viram raw

4. **Risco de Confusão:** Múltiplas pastas com mesmo nome (raw, filter, etc.) podem confundir
   - **Mitigação:** Navegação clara e documentação

### Inconsistências

Nenhuma inconsistência identificada no Raw Material.

### Contradições

Nenhuma contradição identificada no Raw Material.

---

## Recomendações

### Para Implementação

1. **Definir processo de transição de artefatos:**
   - Como artefatos de uma role viram raw da próxima
   - Se são copiados, referenciados ou movidos
   - Formato de referência entre roles

2. **Documentar comportamento do agente:**
   - Agente deve identificar role atual
   - Criar arquivos na pasta correta da role
   - Manter numeração adequada

3. **Criar guia de migração:**
   - Como migrar ciclos existentes
   - Se manter compatibilidade com estrutura antiga
   - Processo de transição

4. **Definir regras para roles opcionais:**
   - Quando criar pasta para role opcional
   - Como indicar que role foi pulada
   - Se manter pasta vazia ou não criar

5. **Atualizar documentação:**
   - README.md com nova estrutura
   - AGENTS.md com comportamento do agente
   - Templates com novos caminhos
   - **Documentar os três pilares fundamentais** (Workspace Agent, Canonical Cycle Agent, MCPs)

### Para Estrutura

1. **Manter numeração no ciclo:** `numeracao_nome_ciclo/`
2. **Pastas de roles sem numeração:** `analista/`, `designer/`, etc.
3. **Pastas de etapas sem numeração:** `raw/`, `filter/`, `canonical/`, `artifacts/`
4. **Arquivos com numeração:** `1_requisitos.md`, `2_anotacoes.md`, etc.

---

## Próximos Passos Sugeridos

1. **Resolver ambiguidades** listadas acima, especialmente:
   - Como artefatos viram raw da próxima role
   - Comportamento para roles opcionais
   - Numeração de arquivos

2. **Definir processo de transição** de artefatos entre roles

3. **Criar exemplo prático** da nova estrutura

4. **Atualizar documentação** (README, AGENTS, GUIDELINES)

5. **Criar guia de migração** se necessário

6. **Atualizar templates** com novos caminhos

7. **Testar nova estrutura** em um ciclo exemplo
8. **Documentar integração dos três pilares** no fluxo de trabalho
9. **Criar seção sobre acesso a contextos** (workspace, regras, externos)

---

**Status:** Proposta de entendimento - aguardando revisão humana para se tornar Canonical Material.
