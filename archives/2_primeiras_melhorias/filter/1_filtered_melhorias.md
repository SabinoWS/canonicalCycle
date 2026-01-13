# Filtered Material - Melhorias do Canonical Cycle

**Referência Raw Material:** `raw/1_conversaWhatsapp.md`
**Gerado em:** 2026-01-13
**Agente:** Agente de Filtragem - Análise
**Role:** Análise

---

## Resumo Executivo

Este material contém melhorias e refinamentos propostos para o Canonical Cycle, focando em:
- Geração de rules e agentes específicos para cada role
- Fluxo detalhado e sequencial entre roles (Analista → Arquiteto → Engenheiro → Desenvolvedor)
- Conceitos importantes: memória por arquivo, artefatos descartáveis, autonomia agentica
- Especificidades e customizações por role/projeto
- Exemplo prático de uso end-to-end

As melhorias visam tornar o ciclo mais prático, com agentes especializados e regras específicas para cada etapa e role.

---

## Informações Estruturadas

### 1. Conceito de Rules e Agentes por Role

**Proposta:** Gerar rules e agentes específicos para cada parte do fluxo do Canonical Cycle.

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

**Definições:**
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

**Definições:**
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

**Definições:**
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

**Conceito:** Cada role/persona pode especificar regras específicas para seu uso.

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

**Conceito importante:**
- **`archives/`** é separado do projeto atual
- `archives/` serve apenas como memória e rastreabilidade dos ciclos
- O projeto atual (fora de `archives/`) é onde o trabalho real acontece

#### 5.5 Destinos do Canonical Material

**O que foi gerado no Canonical Material pode fazer duas coisas:**

1. **Gerar artefatos na pasta `artifacts/`**
   - Artefatos são representações formais (tickets, documentos, etc.)
   - Ficam em `archives/nome_ciclo/artifacts/`
   - São descartáveis e podem ser regenerados

2. **Alterar o projeto atual (fora do `archives/`)**
   - Mudanças diretas no código, documentação ou estrutura do projeto
   - Exemplos: atualizar README.md, modificar código, criar novos arquivos no projeto
   - Essas mudanças são permanentes no projeto

**Decisão:**
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

## Padrões Identificados

1. **Fluxo Sequencial:** Roles seguem ordem: Analista → Arquiteto → Engenheiro → Desenvolvedor
2. **Artefatos como Raw:** Artefatos de uma role se tornam parte do Raw da próxima
3. **Aprovação em Duas Etapas:** Filtered → Canonical sempre requer aprovação humana
4. **Agentes Especializados:** Cada role tem agentes com conhecimento específico
5. **Customização:** Regras podem ser específicas por projeto/contexto

---

## Ambiguidades

> **IMPORTANTE:** Esta seção é obrigatória. Liste todas as ambiguidades encontradas.

### Ambiguidade 1: Processo de Aprovação Filtered → Canonical
- **Descrição:** No exemplo prático, há menção a "agente gerou o canonical" após aprovação do filtered. Não está claro se:
  - O humano aprova o filtered e depois o agente gera o canonical automaticamente?
  - Ou o humano transforma o filtered em canonical manualmente?
- **Contexto:** Passos 4-6 do exemplo do Analista
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 2: Quando Arquiteto é Necessário
- **Descrição:** Exemplo menciona "neste cenário, não tão necessário" para Arquiteto. Não está claro:
  - Quais critérios definem quando Arquiteto é necessário?
  - Quem decide pular a role Arquiteto?
- **Contexto:** Exemplo prático, role Arquiteto
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 3: Formato de "Memória por Arquivo"
- **Descrição:** Conceito mencionado mas não detalhado:
  - Como a memória é armazenada?
  - É um arquivo de metadados? Histórico? Contexto?
  - Como é usado pelos agentes?
- **Contexto:** Conceito importante mencionado
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 4: Regras Específicas por Projeto
- **Descrição:** Mencionado que cada role pode especificar regras, mas não está claro:
  - Onde essas regras são armazenadas? (arquivo de configuração? documentação?)
  - Como são aplicadas pelos agentes?
  - Formato das regras?
- **Contexto:** Customizações por role/projeto
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 5: Integração com Sistemas Externos
- **Descrição:** Exemplo menciona "gerou tickets no Jira" mas não está claro:
  - Agente cria diretamente no Jira ou gera texto para criação manual?
  - Como funciona a integração?
  - Quais outros sistemas são suportados?
- **Contexto:** Geração de artefatos (tickets)
- **Necessita esclarecimento humano:** SIM

---

## Suposições Explícitas

1. **Agentes podem ler código do workspace** - baseado no exemplo do Engenheiro que "lê o código"
2. **Aprovação humana é sempre necessária** - baseado nos passos com ".." (revisão humana) em todos os exemplos
3. **Uma pessoa pode atuar em múltiplas roles** - explicitamente mencionado
4. **Artefatos são texto/estruturados, não código executável** - baseado em "tickets", "tasks", "commit" (exceto desenvolvedor)
5. **Git é usado para versionamento** - baseado em "stage do git" e "commit"
6. **Jira é sistema de tickets padrão** - mencionado múltiplas vezes, mas pode ser customizável

---

## Pontos de Atenção

### Riscos Identificados

1. **Risco de Complexidade:** Múltiplas roles e fluxos podem tornar o processo complexo
   - **Mitigação:** Documentação clara e exemplos

2. **Risco de Dependências:** Fluxo sequencial cria dependências entre roles
   - **Mitigação:** Definir claramente quando roles podem ser puladas

3. **Risco de Customização Excessiva:** Muitas regras específicas podem fragmentar o processo
   - **Mitigação:** Templates e padrões base, com customização opcional

### Inconsistências

1. **Nomenclatura:** Raw Material do Desenvolvedor é "tasks" (que são artefatos de outra role)
   - **Observação:** Isso pode ser intencional (artefatos viram raw), mas precisa ser documentado claramente

### Contradições

Nenhuma contradição identificada no Raw Material.

---

## Recomendações

### Para README.md
1. ✅ Adicionar seção sobre fluxo sequencial entre roles
2. ✅ Documentar como artefatos de uma role viram raw da próxima
3. ✅ Explicar conceitos: memória por arquivo, artefatos descartáveis
4. ✅ Incluir exemplo end-to-end completo
5. ✅ Mencionar possibilidade de customização por projeto

### Para AGENTS.md
1. ✅ Criar seções específicas para cada role (Analista, Arquiteto, Engenheiro, Desenvolvedor)
2. ✅ Documentar como agentes de cada role devem trabalhar
3. ✅ Explicar como agentes leem código/workspace (para Engenheiro)
4. ✅ Documentar processo de aprovação Filtered → Canonical
5. ✅ Adicionar exemplos de prompts por role
6. ✅ Explicar customização de regras por projeto

### Para GUIDELINES.md
1. ✅ Adicionar diretrizes específicas por role
2. ✅ Documentar quando pular roles (ex: Arquiteto)
3. ✅ Explicar processo de aprovação em duas etapas
4. ✅ Adicionar checklist por role

### Para Templates
1. ✅ Criar templates específicos por role
2. ✅ Template para Engenheiro que inclui análise de código
3. ✅ Template para Desenvolvedor focado em código
4. ✅ Templates que suportem customização

### Para Estrutura Geral
1. ✅ Documentar formato de "memória por arquivo"
2. ✅ Criar guia de customização de regras por projeto
3. ✅ Adicionar seção sobre integração com sistemas externos (Jira, Git, etc.)
4. ✅ Documentar fluxo completo end-to-end
5. ✅ Documentar estrutura de pastas `archives/` e regras de numeração
6. ✅ Adicionar diretrizes para agentes sobre criação de arquivos na estrutura correta
7. ✅ Documentar separação entre `archives/` e projeto atual
8. ✅ Explicar os dois destinos possíveis do Canonical Material (artifacts vs. alterações no projeto)

---

## Próximos Passos Sugeridos

1. **Resolver ambiguidades** listadas acima
2. **Atualizar README.md** com fluxo sequencial e conceitos novos
3. **Expandir AGENTS.md** com seções por role
4. **Atualizar GUIDELINES.md** com diretrizes específicas
5. **Criar templates específicos** por role
6. **Documentar customização** de regras por projeto
7. **Criar exemplo end-to-end** completo e documentado
8. **Definir formato** de memória por arquivo
9. **Documentar integrações** com sistemas externos

---

## Impacto nas Melhorias

### Melhorias de Alto Impacto
- ✅ Fluxo sequencial entre roles (mudança estrutural)
- ✅ Agentes especializados por role (mudança de arquitetura)
- ✅ Customização por projeto (flexibilidade)

### Melhorias de Médio Impacto
- ✅ Memória por arquivo (funcionalidade nova)
- ✅ Artefatos descartáveis (conceito a documentar)
- ✅ Estrutura de pastas `archives/` e numeração (organização)
- ✅ Exemplo prático end-to-end (documentação)

### Melhorias de Baixo Impacto
- ✅ Ajustes em nomenclatura
- ✅ Melhorias em templates

---

**Status:** Proposta de entendimento - aguardando revisão humana para se tornar Canonical Material.
