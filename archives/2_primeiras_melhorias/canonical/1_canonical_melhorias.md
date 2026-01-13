# Canonical Material - Melhorias do Canonical Cycle

**Versão:** v1.0
**Aprovado em:** 2026-01-13
**Aprovador:** [A ser preenchido]
**Referência Filtered Material:** `filter/1_filtered_melhorias.md`
**Role:** Análise

---

## Status

✅ **Aprovado como Canonical Material**

Este material foi revisado, ajustado e aprovado como fonte oficial de verdade para as próximas etapas.

---

## Conteúdo Validado

### 1. Rules e Agentes por Role

**Conceito Aprovado:** Gerar rules e agentes específicos para cada parte do fluxo do Canonical Cycle.

**Implicações:**
- Cada role terá seu próprio conjunto de regras
- Agentes especializados para cada etapa (Raw → Filtered → Canonical → Artifacts)
- Customização por projeto/contexto

---

### 2. Fluxo Detalhado por Role

#### 🧠 Role: Analista

**Fluxo:**
```
Raw → Filtered → Canonical → Artifacts
```

**Definições Aprovadas:**
- **Raw:** Conversa com cliente, anotações, fotos, documentos, relatos, prints
- **Filtered:** IA organizando e estruturando o Raw Material
- **Canonical:** Material aprovado pelo analista responsável, que permite gerar artefatos a qualquer momento
- **Artifacts:** Análise de negócio, requisitos, épicos e histórias

**Características:**
- Artefatos passam para a próxima role (Arquiteto)

---

#### 🏗️ Role: Arquiteto

**Fluxo:**
```
Raw → Filtered → Canonical → Artifacts
```

**Definições Aprovadas:**
- **Raw:** Artefato da role anterior (Análise) + coisas raw de levantamentos próprios do arquiteto
- **Filtered:** IA organizando e estruturando
- **Canonical:** Material aprovado pelo arquiteto responsável
- **Artifacts:** Artefatos arquiteturais (ADRs, diagramas, decisões técnicas)

**Características:**
- Recebe artefatos da role anterior como parte do Raw Material
- Pode adicionar seu próprio Raw Material (levantamentos técnicos)
- Artefatos passam para a próxima role (Engenheiro)

**Observação:** Pode não ser necessário em todos os cenários (exemplo: correção de bugs simples)

---

#### ⚙️ Role: Engenheiro

**Fluxo:**
```
Raw → Filtered → Canonical → Artifacts
```

**Definições Aprovadas:**
- **Raw:** Tickets/artefatos da role anterior + contexto de workspace (código)
- **Filtered:** Levantamento filtrado sobre ajustes, impactos, esforço e onde mexer exatamente
- **Canonical:** Tasks detalhadas aprovadas
- **Artifacts:** Tickets no Jira com tasks detalhadas

**Características:**
- Agente lê tickets anteriores e código do workspace
- Cria análise técnica (impactos, esforço, localização exata das mudanças)
- Gera tasks detalhadas da história
- Cria tickets no Jira

---

#### 💻 Role: Desenvolvedor

**Fluxo:**
```
Raw → Filtered → Canonical → Artifacts
```

**Definições Aprovadas:**
- **Raw:** Tasks (recebidas da role anterior)
- **Filtered:** Alterações no workspace (código) feitas pelo agente
- **Canonical:** Stage do git (código pronto para commit)
- **Artifacts:** Commit

**Características:**
- Foco em implementação de código
- Filtered = código gerado/modificado pelo agente
- Canonical = código revisado e staged no git
- Artifact = commit final

---

### 3. Conceitos Importantes

#### 3.1 Memória por Arquivo
- Cada arquivo deve ter sua própria memória/contexto
- Permite rastreabilidade e histórico por arquivo
- Facilita geração de artefatos a partir de canonicals específicos

#### 3.2 Artefatos Descartáveis
- Artefatos podem ser gerados a qualquer momento a partir do Canonical Material
- Artefatos são descartáveis (podem ser regenerados)
- Canonical Material é a fonte de verdade, não os artefatos

#### 3.3 Autonomia Agentica com Responsabilidade Técnica
- Agentes têm autonomia para processar e gerar
- Responsabilidade técnica fica com as personas que aprovam os canonicals
- Uma mesma pessoa pode atuar em múltiplas personas/roles

---

### 4. Especificidades e Customizações por Role/Projeto

**Conceito Aprovado:** Cada role/persona pode especificar regras específicas para seu uso.

**Exemplos de customizações:**
- **Analista:** Como o agente deve escrever tickets, formato de requisitos
- **Arquiteto:** Boas práticas específicas para arquitetura, padrões a seguir
- **Engenheiro:** Como estruturar tasks, critérios de aceite
- **Desenvolvedor:** Como escrever código, padrões de código, estilo específico do projeto

**Implicação:**
- README, AGENTS.md e outros documentos devem permitir/suportar essas customizações
- Templates devem ser flexíveis
- Regras podem ser definidas por projeto

---

### 5. Estrutura de Pastas e Numeração

#### 5.1 Estrutura de Diretórios

**Estrutura padrão do Canonical Cycle:**

```
archives/
└── nome_ciclo/
    ├── raw/
    ├── filter/
    ├── canonical/
    └── artifacts/
```

**Regras importantes:**
- **`archives/`** é onde a memória dos ciclos fica no projeto ou workspace
- **`archives/` NÃO faz parte do projeto** - é separado, apenas para memória e rastreabilidade
- Cada ciclo tem sua própria pasta dentro de `archives/`
- Cada ciclo contém as 4 etapas: `raw/`, `filter/`, `canonical/`, `artifacts/`
- **Pastas das etapas NÃO devem ter numeração** (ex: `raw/`, não `1_raw/`)

#### 5.2 Numeração

**Regras de numeração:**
1. **Nome do ciclo:** Deve começar com numeração indicando ordem de criação
   - Exemplo: `1_inicio_projeto`, `2_primeiras_melhorias`, `3_nova_feature`
   
2. **Arquivos dentro das etapas:** Devem começar com numeração indicando ordem de criação
   - Exemplo: `1_conversaWhatsapp.md`, `2_requisitos.md`, `3_anotacoes.md`
   - Numeração no início do nome do arquivo
   
3. **Pastas das etapas:** NÃO devem ter numeração
   - ✅ Correto: `raw/`, `filter/`, `canonical/`, `artifacts/`
   - ❌ Incorreto: `1_raw/`, `2_filter/`

#### 5.3 Comportamento do Agente

**Quando processar Raw Material:**
- O agente deve identificar em qual ciclo está trabalhando (pela localização do arquivo raw)
- Deve criar o Filtered Material na pasta `filter/` do mesmo ciclo
- Deve seguir a numeração: se o raw é `1_conversaWhatsapp.md`, o filtered deve ser `1_filtered_conversaWhatsapp.md` (ou similar, mantendo numeração)

**Exemplo prático:**
```
archives/
└── 2_primeiras_melhorias/
    ├── raw/
    │   └── 1_conversaWhatsapp.md
    ├── filter/
    │   └── 1_filtered_melhorias.md  ← Agente cria aqui, no mesmo ciclo
    ├── canonical/
    └── artifacts/
```

**Responsabilidades do agente:**
- ✅ Identificar o ciclo atual pela estrutura de pastas
- ✅ Criar arquivos na pasta correta do ciclo
- ✅ Manter numeração sequencial nos arquivos
- ✅ Respeitar estrutura: `archives/nome_ciclo/{raw,filter,canonical,artifacts}/`

#### 5.4 Separação entre Archives e Projeto

**Conceito Aprovado:**
- **`archives/`** é separado do projeto atual
- `archives/` serve apenas como memória e rastreabilidade dos ciclos
- O projeto atual (fora de `archives/`) é onde o trabalho real acontece

#### 5.5 Destinos do Canonical Material

**Conceito Aprovado:** O que foi gerado no Canonical Material pode fazer duas coisas:

1. **Gerar artefatos na pasta `artifacts/`**
   - Artefatos são representações formais (tickets, documentos, etc.)
   - Ficam em `archives/nome_ciclo/artifacts/`
   - São descartáveis e podem ser regenerados
   - Usados para referência ou publicação em sistemas externos

2. **Alterar o projeto atual (fora do `archives/`)**
   - Mudanças diretas no código, documentação ou estrutura do projeto
   - Exemplos: atualizar README.md, modificar código, criar novos arquivos no projeto
   - Essas mudanças são permanentes no projeto
   - Implementações diretas baseadas no Canonical Material

**Regras:**
- O Canonical Material deve indicar qual destino será usado
- Pode usar ambos os destinos simultaneamente
- Artefatos em `artifacts/` são para referência/publicação
- Alterações no projeto são implementações diretas

---

### 6. Exemplo Prático End-to-End

#### Cenário: Correção de Bugs no Mapa

**Contexto:** Suporte reportou problemas no mapa (relato + prints)

##### Analista
1. ✅ Colocou relato e prints em `relatoMapa/raw`
2. ✅ No prompt, forneceu pensamento e acesso ao raw
3. ✅ Agente analista criou filtered com cenários de ajustes
4. ✅ Revisou filtered, fez refinamentos pequenos e aprovou
5. ✅ Agente gerou canonical
6. ✅ Aprovou canonical
7. ✅ Agente gerou tickets no Jira

##### Arquiteto
- **Neste cenário:** Não foi necessário (correção simples)

##### Engenheiro
1. ✅ Iniciou prompt enviando os tickets
2. ✅ Agente leu tickets, leu código (workspace), criou filtered sobre:
   - Ajustes necessários
   - Impactos
   - Esforço
   - Onde mexer exatamente
3. ✅ Revisou filtered, ajustou se necessário, aprovou
4. ✅ Agente criou tasks detalhadas da história
5. ✅ Aprovou tasks
6. ✅ Agente criou tickets no Jira

##### Desenvolvedor
- Raw = tasks recebidas
- Filtered = alterações no código feitas pelo agente
- Canonical = código staged no git
- Artifact = commit

---

### 7. Padrões Identificados

1. **Fluxo Sequencial:** Roles seguem ordem: Analista → Arquiteto → Engenheiro → Desenvolvedor
2. **Artefatos como Raw:** Artefatos de uma role se tornam parte do Raw da próxima
3. **Aprovação em Duas Etapas:** Filtered → Canonical sempre requer aprovação humana
4. **Agentes Especializados:** Cada role tem agentes com conhecimento específico
5. **Customização:** Regras podem ser específicas por projeto/contexto

---

## Decisões Tomadas Durante Revisão

### Decisão 1: Processo de Aprovação Filtered → Canonical
- **Ambiguidade original:** Não estava claro se o humano aprova o filtered e depois o agente gera o canonical automaticamente, ou se o humano transforma manualmente
- **Decisão:** O humano revisa e aprova o Filtered Material, e então o agente pode gerar o Canonical Material automaticamente baseado no Filtered aprovado. O humano então revisa e aprova o Canonical Material final.
- **Justificativa:** Mantém a responsabilidade humana na aprovação, mas permite automação na geração do formato Canonical a partir do Filtered aprovado.

### Decisão 2: Quando Arquiteto é Necessário
- **Ambiguidade original:** Não estava claro quais critérios definem quando Arquiteto é necessário
- **Decisão:** Arquiteto é necessário quando há decisões arquiteturais significativas, mudanças estruturais, ou necessidade de definir padrões técnicos. Pode ser pulado para correções simples, ajustes pontuais ou quando decisões arquiteturais já estão estabelecidas.
- **Justificativa:** Flexibilidade no processo permite eficiência sem comprometer qualidade quando decisões arquiteturais são necessárias.

### Decisão 3: Formato de "Memória por Arquivo"
- **Ambiguidade original:** Conceito mencionado mas não detalhado
- **Decisão:** A memória por arquivo é a estrutura de pastas `archives/` onde cada ciclo mantém seu histórico completo (raw, filter, canonical, artifacts). Cada arquivo dentro de um ciclo mantém referências ao seu ciclo e pode ser rastreado através da estrutura de pastas.
- **Justificativa:** A estrutura de pastas `archives/` já implementa o conceito de memória por arquivo de forma prática e rastreável.

### Decisão 4: Regras Específicas por Projeto
- **Ambiguidade original:** Não estava claro onde e como regras são armazenadas e aplicadas
- **Decisão:** Regras específicas por projeto podem ser definidas em arquivos de configuração (ex: `.canonical-cycle.yml`) ou documentação específica do projeto. Agentes devem ler essas regras ao processar material do projeto.
- **Justificativa:** Permite customização mantendo padrão base. Formato específico será definido em implementação futura.

### Decisão 5: Integração com Sistemas Externos
- **Ambiguidade original:** Não estava claro se agentes criam diretamente nos sistemas ou geram texto
- **Decisão:** Por padrão, agentes geram artefatos como texto formatado pronto para publicação, mas não publicam automaticamente. Integração direta com sistemas (Jira, Git, etc.) pode ser configurada por projeto, mas requer aprovação explícita do humano.
- **Justificativa:** Mantém controle humano sobre publicação, mas permite automação quando configurada e aprovada.

---

## Suposições Validadas

1. ✅ **Agentes podem ler código do workspace** - validado, necessário para role de Engenheiro
2. ✅ **Aprovação humana é sempre necessária** - validado, cada etapa Filtered → Canonical requer aprovação
3. ✅ **Uma pessoa pode atuar em múltiplas roles** - validado, explicitamente mencionado e aprovado
4. ✅ **Artefatos são texto/estruturados, não código executável** - validado, exceto para role de Desenvolvedor onde Filtered e Canonical são código
5. ✅ **Git é usado para versionamento** - validado, usado na role de Desenvolvedor
6. ✅ **Jira é sistema de tickets padrão** - validado como exemplo, mas customizável por projeto

---

## Correções Realizadas

- Estrutura de pastas `archives/` e numeração adicionada como seção oficial
- Comportamento do agente em relação à estrutura de pastas documentado
- Decisões sobre ambiguidades documentadas

---

## Histórico de Versões

| Versão | Data | Aprovador | Mudanças |
|--------|------|-----------|----------|
| v1.0 | 2026-01-13 | [A ser preenchido] | Versão inicial aprovada |

---

## Pronto para Geração de Artefatos

✅ Este Canonical Material está pronto para ser usado como fonte para geração de artefatos.

**Artefatos sugeridos:**
- Atualização do README.md com fluxo sequencial e novos conceitos
- Expansão do AGENTS.md com seções específicas por role
- Atualização do GUIDELINES.md com diretrizes específicas
- Criação de templates específicos por role
- Documentação da estrutura de pastas `archives/` e numeração
- Guia de customização de regras por projeto
- Documentação da separação entre `archives/` e projeto atual
- Explicação dos dois destinos possíveis do Canonical Material (artifacts vs. alterações no projeto)

**Regra:** Qualquer alteração relevante neste material requer novo Canonical Cycle.

---

**Nota:** Este é material canônico - fonte única de verdade. Não será reinterpretado sem novo ciclo.
