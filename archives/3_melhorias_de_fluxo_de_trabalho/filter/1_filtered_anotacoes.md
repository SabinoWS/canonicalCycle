# Filtered Material - Melhorias no Fluxo de Trabalho do Canonical Cycle

**Referência Raw Material:** `raw/anotacoes.txt`
**Gerado em:** 2026-01-13
**Agente:** Agente de Filtragem - Análise
**Role:** Análise

---

## Resumo Executivo

Este material contém uma estrutura de artefatos/documentação identificada em um processo de desenvolvimento de funcionalidades que pode ser aplicada ao Canonical Cycle para melhorar o fluxo de trabalho dos agentes. A estrutura apresenta uma organização clara de artefatos por etapa, com subitens específicos que podem orientar agentes de cada role sobre o que gerar e como estruturar seus outputs.

A estrutura identificada inclui: Análise de Negócio, Prototipagem (Designer), Análise Técnica, Priorização e Desenvolvimento, com subitens detalhados para cada etapa. O exemplo serve apenas como ilustração de como essa estrutura foi aplicada.

**Nova role identificada:** Designer - responsável por protótipos de tela e UX, role opcional que nem sempre é necessária.

---

## Informações Estruturadas

### 1. Estrutura de Artefatos Identificada

A estrutura apresentada nas anotações pode ser mapeada para as roles do Canonical Cycle:

#### 1.1 Análise de Negócio → Role: Analista

**Artefatos que devem estar no documento:**
- Resumo das necessidades e impacto no produto
- Razão da iniciativa
- Jornada e funcionalidades
- Cenários (história de usuário das funcionalidades)
  - Cenários de sucesso
  - Cenários de falha
- Casos de uso atendidos (exemplos práticos)
- Benchmarks de mercado
- Exemplos de configuração
- Exemplos de validações
- Épico no Jira para guardar tickets maiores para Prototipagem, Análise técnica e Desenvolvimento

**Aplicação ao Canonical Cycle:**
- Agente de Análise deve estruturar Filtered Material incluindo esses elementos
- Canonical Material de Análise deve conter essas seções validadas
- Artifacts de Análise devem incluir esses artefatos formatados

#### 1.2 Prototipagem (se necessário) → Role: Designer

**Artefatos que devem estar no documento:**
- Link Figma (ou ferramenta de prototipagem)
- Protótipo vivo abrindo e fechando em local de abertura (exemplo: view mode Form)
- Prints das telas
- Versão desktop
- Versão mobile

**Aplicação ao Canonical Cycle:**
- Role específica: Designer
- Responsável por protótipos de tela e UX
- Deve ser opcional ("se necessário")
- Agente deve identificar quando prototipagem é necessária
- Fluxo: Analista → Designer (se necessário) → Arquiteto → Engenheiro → Desenvolvedor

#### 1.3 Análise Técnica → Role: Engenheiro

**Artefatos que devem estar no documento:**
- Resumo para Discovery de riscos
- Desenho de arquitetura e fluxo
- Resumo das soluções encontradas
- Tecnologias utilizadas (incluindo bibliotecas e frameworks)
- Timebox máximo para implementação
- Membros responsáveis para desenvolvimento
- Quebra de tarefas em tickets menores para desenvolvimento

**Aplicação ao Canonical Cycle:**
- Agente de Engenharia deve estruturar Filtered Material incluindo esses elementos
- Canonical Material de Engenharia deve conter análise técnica completa
- Artifacts de Engenharia devem incluir tasks detalhadas e tickets

#### 1.4 Priorização das Tarefas (negócio) → Entre Análise e Engenharia

**Aplicação ao Canonical Cycle:**
- Pode ser parte do Canonical Material de Análise
- Ou pode ser uma etapa intermediária entre Análise e Engenharia
- Define ordem de execução das tasks

#### 1.5 Desenvolvimento → Role: Desenvolvedor

**Artefatos que devem estar no documento:**
- Alinhamentos com processos anteriores
- Geração de código
- Qualidade
- Deploy em produção

**Aplicação ao Canonical Cycle:**
- Agente de Desenvolvimento trabalha com código (Filtered = código modificado)
- Canonical = código staged
- Artifact = commit

---

### 2. Padrões Identificados na Estrutura

1. **Estrutura Hierárquica Clara:** Cada etapa tem subitens bem definidos
2. **Separação de Responsabilidades:** Cada etapa tem artefatos específicos
3. **Rastreabilidade:** Épico no Jira conecta todas as etapas
4. **Opcionalidade Explícita:** Prototipagem marcada como "se necessário" → Role Designer opcional
5. **Priorização Explícita:** Etapa dedicada à priorização
6. **Foco em Riscos:** Análise técnica inclui discovery de riscos
7. **Detalhamento Progressivo:** De análise de negócio até desenvolvimento técnico
8. **Múltiplas Roles Opcionais:** Tanto Designer quanto Arquiteto podem ser opcionais

---

### 3. Mapeamento para Canonical Cycle

#### 3.1 Role: Analista

**Filtered Material deve incluir:**
- Resumo das necessidades e impacto
- Razão da iniciativa
- Jornada e funcionalidades
- Cenários (sucesso e falha)
- Casos de uso
- Benchmarks (se aplicável)
- Exemplos de configuração e validação

**Canonical Material deve conter:**
- Todas as seções acima validadas
- Épico criado/referenciado no Jira

**Artifacts devem incluir:**
- Análise de negócio formatada
- Requisitos estruturados
- Épico e histórias no Jira

#### 3.2 Role: Designer (quando necessário)

**Fluxo:**
```
Raw Material -> Filtered Material -> Canonical Material -> Design Artifacts
```

**Definições:**
- **Raw:** Artefatos da role anterior (Análise) + requisitos de UX/UI
- **Filtered:** Protótipos e designs estruturados pela IA
- **Canonical:** Protótipos aprovados pelo designer responsável
- **Artifacts:** Protótipos de tela, designs, links Figma, prints

**Filtered Material deve incluir:**
- Protótipos de tela (desktop e mobile)
- Fluxos de UX
- Design system aplicado
- Links para ferramentas de prototipagem (Figma, etc.)
- Prints das telas

**Canonical Material deve conter:**
- Protótipos aprovados
- Design final validado
- Especificações de UX/UI

**Artifacts devem incluir:**
- Links Figma (ou ferramenta de prototipagem)
- Protótipo vivo
- Prints das telas
- Versão desktop
- Versão mobile

**Características:**
- Recebe artefatos da role anterior (Análise) como parte do Raw Material
- Foco em protótipos de tela e experiência do usuário
- Artefatos passam para a próxima role (Arquiteto ou Engenheiro)

**Observação:** Pode não ser necessário em todos os cenários (exemplo: funcionalidades backend, correções simples, melhorias técnicas)

#### 3.3 Role: Arquiteto (quando necessário)

**Filtered Material deve incluir:**
- Desenho de arquitetura e fluxo
- Decisões arquiteturais
- Padrões técnicos

**Canonical Material deve conter:**
- Arquitetura aprovada
- ADRs (Architecture Decision Records)

**Artifacts devem incluir:**
- Diagramas arquiteturais
- ADRs formatados

#### 3.4 Role: Engenheiro

**Filtered Material deve incluir:**
- Resumo para Discovery de riscos
- Análise técnica detalhada
- Soluções encontradas
- Tecnologias utilizadas
- Timebox e estimativas
- Membros responsáveis
- Quebra de tarefas em tickets menores

**Canonical Material deve conter:**
- Análise técnica aprovada
- Tasks detalhadas validadas
- Priorização definida

**Artifacts devem incluir:**
- Plano técnico
- Tasks detalhadas
- Tickets no Jira

#### 3.5 Role: Desenvolvedor

**Filtered Material:**
- Código modificado/gerado

**Canonical Material:**
- Código revisado e staged

**Artifacts:**
- Commit

---

## Padrões Identificados

1. **Estrutura Hierárquica:** Cada role tem artefatos específicos bem definidos
2. **Rastreabilidade:** Épico conecta todas as etapas
3. **Opcionalidade:** Algumas etapas são opcionais (ex: Prototipagem, Arquiteto)
4. **Priorização Explícita:** Etapa dedicada à priorização entre análise e desenvolvimento
5. **Foco em Riscos:** Análise técnica sempre inclui discovery de riscos
6. **Detalhamento Progressivo:** Nível de detalhe aumenta conforme avança no fluxo
7. **Separação Clara:** Cada etapa tem responsabilidades bem definidas

---

## Ambiguidades

> **IMPORTANTE:** Esta seção é obrigatória. Liste todas as ambiguidades encontradas.

### Ambiguidade 1: Quando Designer é Necessário?
- **Descrição:** Designer é uma role opcional. Não está claro:
  - Quais critérios definem quando Designer é necessário?
  - Quem decide incluir a role Designer?
  - Em que casos pode ser pulada?
- **Contexto:** Role Designer, prototipagem
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 2: Fluxo com Designer
- **Descrição:** Com a adição da role Designer, o fluxo pode ser:
  - Analista → Designer → Arquiteto → Engenheiro → Desenvolvedor
  - Analista → Designer → Engenheiro → Desenvolvedor (pulando Arquiteto)
  - Analista → Arquiteto → Engenheiro → Desenvolvedor (pulando Designer)
  Não está claro quando cada fluxo deve ser usado.
- **Contexto:** Fluxo sequencial com role opcional Designer
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 3: Priorização como Etapa Separada?
- **Descrição:** Priorização aparece como etapa separada entre Análise Técnica e Desenvolvimento. Não está claro se é:
  - Parte do Canonical Material de Análise?
  - Parte do Canonical Material de Engenharia?
  - Uma etapa intermediária própria?
- **Contexto:** Estrutura de artefatos, Priorização
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 4: Benchmarks de Mercado
- **Descrição:** Benchmarks são mencionados na estrutura mas não aparecem no exemplo. Não está claro:
  - Quando são necessários?
  - Como devem ser apresentados?
  - Quem é responsável (Analista ou Arquiteto)?
- **Contexto:** Estrutura de artefatos, Análise de Negócio
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 5: Timebox e Estimativas
- **Descrição:** Timebox aparece na Análise Técnica, mas não está claro:
  - Deve ser estimativa inicial ou final?
  - Quem valida (Engenheiro ou gestor)?
  - Como isso se relaciona com o Canonical Material?
- **Contexto:** Análise Técnica, Timebox
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 6: Membros Responsáveis
- **Descrição:** "Membros responsáveis para desenvolvimento" aparece na Análise Técnica. Não está claro:
  - Isso deve estar no Canonical Material?
  - É informação para o agente ou para o humano?
  - Como isso se relaciona com o fluxo do Canonical Cycle?
- **Contexto:** Análise Técnica, Membros responsáveis
- **Necessita esclarecimento humano:** SIM

---

## Suposições Explícitas

1. **Estrutura pode ser aplicada ao Canonical Cycle:** A estrutura apresentada serve como template para melhorar o fluxo
2. **Cada role deve gerar artefatos específicos:** Baseado na estrutura identificada
3. **Épico conecta todas as etapas:** Serve como rastreabilidade entre roles
4. **Designer é role opcional:** Pode não ser necessária em todos os casos (funcionalidades backend, correções simples, melhorias técnicas)
5. **Prototipagem é responsabilidade do Designer:** Role específica para protótipos de tela e UX
6. **Priorização é importante:** Deve haver uma etapa explícita de priorização
7. **Riscos devem ser identificados:** Análise técnica sempre deve incluir discovery de riscos
8. **Detalhamento progressivo:** Cada etapa adiciona mais detalhes técnicos
9. **Fluxo flexível:** Com roles opcionais (Designer e Arquiteto), o fluxo pode variar conforme necessidade

---

## Pontos de Atenção

### Riscos Identificados

1. **Risco de Complexidade:** Adicionar muitos subitens pode tornar o processo complexo
   - **Mitigação:** Manter estrutura flexível, alguns itens podem ser opcionais

2. **Risco de Rigidez:** Estrutura muito rígida pode não se adequar a todos os projetos
   - **Mitigação:** Manter itens opcionais e customizáveis por projeto

3. **Risco de Duplicação:** Alguns artefatos podem se sobrepor entre roles
   - **Mitigação:** Definir claramente responsabilidades de cada role

### Inconsistências

Nenhuma inconsistência identificada no Raw Material.

### Contradições

Nenhuma contradição identificada no Raw Material.

---

## Recomendações

### Para Melhorar o Fluxo do Canonical Cycle

1. **Estruturar Templates por Role:**
   - Criar templates específicos para cada role baseados na estrutura identificada
   - Templates devem incluir os subitens relevantes para cada role
   - **Adicionar template específico para role Designer**

2. **Adicionar Seções ao AGENTS.md:**
   - Documentar quais artefatos cada role deve gerar
   - Incluir checklist de artefatos esperados por role
   - **Adicionar seção específica para Agente Designer**

3. **Melhorar Templates Existentes:**
   - Atualizar templates de Filtered Material com seções específicas por role
   - Adicionar seções para: cenários, casos de uso, riscos, timebox, etc.
   - **Criar template de Filtered Material para Designer**

4. **Documentar Priorização:**
   - Definir onde e como a priorização acontece no fluxo
   - Criar template ou seção específica para priorização

5. **Adicionar Rastreabilidade:**
   - Documentar como épicos/tickets conectam as etapas
   - Incluir referências cruzadas entre artefatos

6. **Definir Opcionalidade:**
   - **Documentar quando Designer é necessário** (critérios claros)
   - Documentar quando Arquiteto é necessário
   - Criar critérios claros para ambas as roles opcionais
   - **Documentar fluxos possíveis** com diferentes combinações de roles opcionais

### Para Templates

1. **Template de Análise:**
   - Incluir seções: resumo, razão, jornada, cenários, casos de uso, benchmarks, exemplos
   - Seção para épico no Jira

2. **Template de Designer (quando necessário):**
   - Links Figma (ou ferramenta de prototipagem)
   - Protótipo vivo
   - Prints das telas
   - Versão desktop
   - Versão mobile
   - Fluxos de UX
   - Design system aplicado

3. **Template de Engenharia:**
   - Incluir seções: discovery de riscos, arquitetura/fluxo, soluções, tecnologias, timebox, membros, quebra de tarefas
   - Foco em análise técnica detalhada

---

## Próximos Passos Sugeridos

1. **Resolver ambiguidades** listadas acima
2. **Criar templates específicos** por role baseados na estrutura identificada
   - **Incluir template para role Designer**
3. **Atualizar AGENTS.md** com artefatos esperados por role
   - **Adicionar seção específica para Agente Designer**
4. **Atualizar templates existentes** com novas seções
5. **Documentar processo de priorização** no fluxo
6. **Definir critérios de opcionalidade** (Designer, Arquiteto)
   - **Criar critérios claros para quando Designer é necessário**
   - **Documentar fluxos possíveis** com diferentes combinações
7. **Criar guia de rastreabilidade** (épicos, tickets, referências cruzadas)
8. **Atualizar README.md** com a nova role Designer no fluxo sequencial

---

**Status:** Proposta de entendimento - aguardando revisão humana para se tornar Canonical Material.
