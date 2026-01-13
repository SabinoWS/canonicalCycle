# Canonical Cycle

**Referência Canonical:** `archives/2_primeiras_melhorias/canonical/1_canonical_melhorias.md` v1.0

---

## Visão Geral

O **Canonical Cycle** é um fluxo de trabalho controlado no qual informações brutas são processadas por IA, validadas por humanos e consolidadas em material canônico antes da geração de artefatos e entrega de software.

### Princípio Fundamental

Cria um contrato explícito entre IA e humano:
- **IA nunca decide verdade** - apenas propõe interpretações
- **Humano nunca reinterpreta material bruto sem IA** - usa o fluxo estruturado
- **Canonical Material é o ponto de responsabilidade** - onde a verdade é estabelecida

---

## Fluxo do Canonical Cycle

```
Raw Material
   -> Filtered Material
      -> Canonical Material
         -> Artifacts
            -> Delivery
```

**`->`** = revisão / decisão humana explícita

**Regra de reentrância:** Qualquer alteração relevante → novo Canonical Cycle

---

## Estágios do Ciclo

### 🧱 Raw Material
Dados brutos e não estruturados, coletados sem interpretação.
- Anotações livres, atas de reunião, entrevistas, imagens, etc.
- **Nenhuma validação, nenhuma verdade assumida**

### 🔍 Filtered Material
Material interpretado e estruturado pela IA a partir do Raw Material.
- Resumos, agrupamentos, hipóteses, ambiguidades identificadas
- **Ainda não é oficial - é uma proposta de entendimento**

### 🏛️ Canonical Material
Material revisado, ajustado e aprovado por humano.
- Fonte oficial de verdade para as próximas etapas
- **Aqui a ambiguidade termina**

### 📄 Artifacts
Representações formais de entregáveis reais, ainda não publicadas.
- Tickets, documentos, planos técnicos, etc.
- **Prontos para entrega, aguardando publicação**

### 🚀 Delivery
Criação efetiva do artefato no sistema de destino.
- Criar ticket no Jira, abrir PR, publicar documento, deploy, etc.

---

## Quick Start

1. **Crie um ciclo** em `archives/nome_ciclo/` (ex: `archives/1_nova_feature/`)
2. **Colete Raw Material** em `archives/nome_ciclo/raw/`
3. **Use um agente de IA** para gerar Filtered Material na pasta `filter/` do mesmo ciclo (veja [AGENTS.md](./AGENTS.md))
4. **Revise e aprove** o Filtered Material como Canonical Material em `canonical/` (veja [GUIDELINES.md](./GUIDELINES.md))
5. **Gere artefatos** a partir do Canonical Material:
   - Artefatos em `archives/nome_ciclo/artifacts/` OU
   - Alterações diretas no projeto atual (fora de `archives/`)
6. **Execute o Delivery** publicando os artefatos ou implementando as mudanças

**Importante:** O agente deve identificar automaticamente o ciclo pela estrutura de pastas e criar arquivos na pasta correta do ciclo.

Para um exemplo completo, veja [examples/analysis-cycle/](./examples/analysis-cycle/).

---

## Estrutura do Repositório

```
canonicalCycle/
├── README.md              # Este arquivo
├── AGENTS.md              # Diretrizes para agentes de IA
├── GUIDELINES.md           # Diretrizes para humanos
├── templates/              # Templates para cada estágio
│   ├── raw-material-template.md
│   ├── filtered-material-template.md
│   ├── canonical-material-template.md
│   └── artifacts/
├── examples/               # Exemplos completos
│   ├── analysis-cycle/
│   ├── architecture-cycle/
│   └── engineering-cycle/
└── archives/              # Memória dos ciclos (separado do projeto)
    └── nome_ciclo/
        ├── raw/
        ├── filter/
        ├── canonical/
        └── artifacts/
```

**Importante:** A pasta `archives/` **NÃO faz parte do projeto** - é separada e serve apenas como memória e rastreabilidade dos ciclos. O projeto atual (fora de `archives/`) é onde o trabalho real acontece.

---

## Fluxo Sequencial por Role

O Canonical Cycle segue um **fluxo sequencial** entre roles, onde os artefatos de uma role se tornam parte do Raw Material da próxima:

```
Analista → Arquiteto → Engenheiro → Desenvolvedor
```

### 🧠 Role: Analista

**Fluxo:**
```
Raw Material -> Filtered Material -> Canonical Material -> Analysis Artifacts
```

**Definições:**
- **Raw:** Conversa com cliente, anotações, fotos, documentos, relatos, prints
- **Filtered:** IA organizando e estruturando o Raw Material
- **Canonical:** Material aprovado pelo analista responsável
- **Artifacts:** Análise de negócio, requisitos, épicos e histórias

**Saída:** Artefatos passam para a próxima role (Arquiteto)

### 🏗️ Role: Arquiteto

**Fluxo:**
```
Raw Material -> Filtered Material -> Canonical Material -> Architecture Artifacts
```

**Definições:**
- **Raw:** Artefato da role anterior (Análise) + coisas raw de levantamentos próprios do arquiteto
- **Filtered:** IA organizando e estruturando
- **Canonical:** Material aprovado pelo arquiteto responsável
- **Artifacts:** Artefatos arquiteturais (ADRs, diagramas, decisões técnicas)

**Saída:** Artefatos passam para a próxima role (Engenheiro)

**Observação:** Pode não ser necessário em todos os cenários (exemplo: correção de bugs simples)

### ⚙️ Role: Engenheiro

**Fluxo:**
```
Raw Material -> Filtered Material -> Canonical Material -> Engineering Artifacts
```

**Definições:**
- **Raw:** Tickets/artefatos da role anterior + contexto de workspace (código)
- **Filtered:** Levantamento filtrado sobre ajustes, impactos, esforço e onde mexer exatamente
- **Canonical:** Tasks detalhadas aprovadas
- **Artifacts:** Tickets no Jira com tasks detalhadas

**Características:**
- Agente lê tickets anteriores e código do workspace
- Cria análise técnica (impactos, esforço, localização exata das mudanças)

**Saída:** Tasks detalhadas passam para a próxima role (Desenvolvedor)

### 💻 Role: Desenvolvedor

**Fluxo:**
```
Raw Material -> Filtered Material -> Canonical Material -> Artifacts
```

**Definições:**
- **Raw:** Tasks (recebidas da role anterior)
- **Filtered:** Alterações no workspace (código) feitas pelo agente
- **Canonical:** Stage do git (código pronto para commit)
- **Artifacts:** Commit

**Características:**
- Foco em implementação de código
- Filtered = código gerado/modificado pelo agente
- Canonical = código revisado e staged no git
- Artifact = commit final

**Saída:** Entrega real (código commitado, tickets criados, PRs abertos, etc.)

---

## Conceitos Importantes

### Memória por Arquivo
- Cada arquivo mantém sua própria memória/contexto através da estrutura `archives/`
- Permite rastreabilidade e histórico por arquivo
- Facilita geração de artefatos a partir de canonicals específicos

### Artefatos Descartáveis
- Artefatos podem ser gerados a qualquer momento a partir do Canonical Material
- Artefatos são descartáveis (podem ser regenerados)
- Canonical Material é a fonte de verdade, não os artefatos

### Autonomia Agentica com Responsabilidade Técnica
- Agentes têm autonomia para processar e gerar
- Responsabilidade técnica fica com as personas que aprovam os canonicals
- Uma mesma pessoa pode atuar em múltiplas personas/roles

### Destinos do Canonical Material

O Canonical Material pode ter **dois destinos**:

1. **Gerar artefatos na pasta `artifacts/`**
   - Artefatos são representações formais (tickets, documentos, etc.)
   - Ficam em `archives/nome_ciclo/artifacts/`
   - São descartáveis e podem ser regenerados
   - Usados para referência ou publicação em sistemas externos

2. **Alterar o projeto atual (fora do `archives/`)**
   - Mudanças diretas no código, documentação ou estrutura do projeto
   - Exemplos: atualizar README.md, modificar código, criar novos arquivos
   - Essas mudanças são permanentes no projeto
   - Implementações diretas baseadas no Canonical Material

Ambos os destinos podem ser usados simultaneamente.

---

## Regras Fundamentais

1. ❌ **Nada gera artefato sem Canonical Material**
2. ❌ **Canonical Material não nasce da IA sozinho** - requer aprovação humana
3. ✅ **Toda decisão tem um ponto humano explícito**
4. 🔁 **Mudou o contexto? Novo ciclo**
5. 📌 **Artefatos sempre referenciam um Canonical**
6. 🔄 **Artefatos de uma role se tornam Raw da próxima** (fluxo sequencial)

---

## Documentação

- **[AGENTS.md](./AGENTS.md)** - Diretrizes detalhadas para agentes de IA
- **[GUIDELINES.md](./GUIDELINES.md)** - Diretrizes e checklists para humanos
- **[templates/](./templates/)** - Templates para cada estágio do ciclo
- **[examples/](./examples/)** - Exemplos completos de uso