# Canonical Material - Melhorias no Fluxo de Trabalho do Canonical Cycle

**Versão:** v1.0
**Aprovado em:** 2026-01-13
**Aprovador:** [A ser preenchido]
**Referência Filtered Material:** `filter/1_filtered_anotacoes.md`
**Role:** Análise

---

## Status

✅ **Aprovado como Canonical Material**

Este material foi revisado, ajustado e aprovado como fonte oficial de verdade para as próximas etapas.

---

## Conteúdo Validado

### 1. Estrutura de Artefatos por Role

A estrutura identificada nas anotações foi mapeada e aprovada para aplicação no Canonical Cycle:

#### 1.1 Role: Analista

**Artefatos que devem estar no documento:**
- Resumo das necessidades e impacto no produto
- Razão da iniciativa
- Jornada e funcionalidades
- Cenários (história de usuário das funcionalidades)
  - Cenários de sucesso
  - Cenários de falha
- Casos de uso atendidos (exemplos práticos)
- Benchmarks de mercado (quando aplicável)
- Exemplos de configuração
- Exemplos de validações
- Épico no Jira para guardar tickets maiores para Prototipagem, Análise técnica e Desenvolvimento

**Aplicação ao Canonical Cycle:**
- Agente de Análise deve estruturar Filtered Material incluindo esses elementos
- Canonical Material de Análise deve conter essas seções validadas
- Artifacts de Análise devem incluir esses artefatos formatados

#### 1.2 Role: Designer (quando necessário)

**Fluxo:**
```
Raw Material -> Filtered Material -> Canonical Material -> Design Artifacts
```

**Definições Aprovadas:**
- **Raw:** Artefatos da role anterior (Análise) + requisitos de UX/UI
- **Filtered:** Protótipos e designs estruturados pela IA
- **Canonical:** Protótipos aprovados pelo designer responsável
- **Artifacts:** Protótipos de tela, designs, links Figma, prints

**Artefatos que devem estar no documento:**
- Link Figma (ou ferramenta de prototipagem)
- Protótipo vivo abrindo e fechando em local de abertura (exemplo: view mode Form)
- Prints das telas
- Versão desktop
- Versão mobile
- Fluxos de UX
- Design system aplicado

**Características:**
- Recebe artefatos da role anterior (Análise) como parte do Raw Material
- Foco em protótipos de tela e experiência do usuário
- Artefatos passam para a próxima role (Arquiteto ou Engenheiro)
- **Role opcional:** Pode não ser necessário em todos os cenários (exemplo: funcionalidades backend, correções simples, melhorias técnicas)

**Fluxo:** Analista → Designer (se necessário) → Arquiteto → Engenheiro → Desenvolvedor

#### 1.3 Role: Engenheiro

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

#### 1.4 Priorização das Tarefas (negócio)

**Aplicação ao Canonical Cycle:**
- Pode ser parte do Canonical Material de Análise
- Ou pode ser uma etapa intermediária entre Análise e Engenharia
- Define ordem de execução das tasks

#### 1.5 Role: Desenvolvedor

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

### 2. Mapeamento Completo para Canonical Cycle

#### 2.1 Role: Analista

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

#### 2.2 Role: Designer (quando necessário)

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

#### 2.3 Role: Arquiteto (quando necessário)

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

#### 2.4 Role: Engenheiro

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

#### 2.5 Role: Desenvolvedor

**Filtered Material:**
- Código modificado/gerado

**Canonical Material:**
- Código revisado e staged

**Artifacts:**
- Commit

---

### 3. Padrões Identificados e Aprovados

1. **Estrutura Hierárquica:** Cada role tem artefatos específicos bem definidos
2. **Rastreabilidade:** Épico conecta todas as etapas
3. **Opcionalidade:** Algumas etapas são opcionais (Designer, Arquiteto)
4. **Priorização Explícita:** Etapa dedicada à priorização entre análise e desenvolvimento
5. **Foco em Riscos:** Análise técnica sempre inclui discovery de riscos
6. **Detalhamento Progressivo:** Nível de detalhe aumenta conforme avança no fluxo
7. **Separação Clara:** Cada etapa tem responsabilidades bem definidas
8. **Múltiplas Roles Opcionais:** Tanto Designer quanto Arquiteto podem ser opcionais

---

## Decisões Tomadas Durante Revisão

### Decisão 1: Quando Designer é Necessário
- **Ambiguidade original:** Não estava claro quais critérios definem quando Designer é necessário
- **Decisão:** Designer é necessário quando há necessidade de protótipos de tela, design de interface ou experiência do usuário. Pode ser pulado para funcionalidades backend, correções simples, melhorias técnicas ou quando design já está estabelecido.
- **Justificativa:** Flexibilidade no processo permite eficiência sem comprometer qualidade quando design é necessário.

### Decisão 2: Fluxo com Designer
- **Ambiguidade original:** Não estava claro quando usar cada combinação de fluxo
- **Decisão:** O fluxo pode variar conforme necessidade:
  - Analista → Designer → Arquiteto → Engenheiro → Desenvolvedor (quando ambos são necessários)
  - Analista → Designer → Engenheiro → Desenvolvedor (quando Arquiteto não é necessário)
  - Analista → Arquiteto → Engenheiro → Desenvolvedor (quando Designer não é necessário)
  - Analista → Engenheiro → Desenvolvedor (quando ambos são desnecessários)
- **Justificativa:** Flexibilidade permite adaptar o processo ao contexto específico de cada projeto.

### Decisão 3: Priorização como Etapa Separada
- **Ambiguidade original:** Não estava claro onde a priorização acontece
- **Decisão:** Priorização pode ser parte do Canonical Material de Análise ou uma seção específica no Canonical Material de Engenharia. Não precisa ser uma etapa separada, mas deve estar explícita.
- **Justificativa:** Priorização é importante mas não precisa ser uma etapa isolada, pode estar integrada nas etapas existentes.

### Decisão 4: Benchmarks de Mercado
- **Ambiguidade original:** Não estava claro quando e como apresentar benchmarks
- **Decisão:** Benchmarks são opcionais e devem ser incluídos quando relevantes para a análise de negócio. Responsabilidade do Analista. Devem ser apresentados como parte da Análise de Negócio.
- **Justificativa:** Benchmarks são úteis mas não obrigatórios em todos os casos.

### Decisão 5: Timebox e Estimativas
- **Ambiguidade original:** Não estava claro se deve ser estimativa inicial ou final
- **Decisão:** Timebox na Análise Técnica deve ser estimativa inicial que será refinada. É responsabilidade do Engenheiro validar e o Canonical Material deve conter a estimativa aprovada.
- **Justificativa:** Estimativas são importantes para planejamento mas podem ser refinadas durante o processo.

### Decisão 6: Membros Responsáveis
- **Ambiguidade original:** Não estava claro onde essa informação deve estar
- **Decisão:** "Membros responsáveis para desenvolvimento" deve estar no Canonical Material de Engenharia como informação de planejamento. É informação para o humano, não para o agente processar.
- **Justificativa:** Informação de planejamento é útil mas não afeta o processamento do agente.

---

## Suposições Validadas

1. ✅ **Estrutura pode ser aplicada ao Canonical Cycle** - validado, serve como template para melhorar o fluxo
2. ✅ **Cada role deve gerar artefatos específicos** - validado, baseado na estrutura identificada
3. ✅ **Épico conecta todas as etapas** - validado, serve como rastreabilidade entre roles
4. ✅ **Designer é role opcional** - validado, pode não ser necessária em todos os casos
5. ✅ **Prototipagem é responsabilidade do Designer** - validado, role específica para protótipos de tela e UX
6. ✅ **Priorização é importante** - validado, deve haver uma etapa explícita de priorização
7. ✅ **Riscos devem ser identificados** - validado, análise técnica sempre deve incluir discovery de riscos
8. ✅ **Detalhamento progressivo** - validado, cada etapa adiciona mais detalhes técnicos
9. ✅ **Fluxo flexível** - validado, com roles opcionais (Designer e Arquiteto), o fluxo pode variar conforme necessidade

---

## Correções Realizadas

- Role Designer adicionada como role opcional oficial
- Fluxos possíveis documentados com diferentes combinações de roles opcionais
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
- Atualização do README.md com role Designer no fluxo sequencial
- Expansão do AGENTS.md com seção específica para Agente Designer
- Atualização do GUIDELINES.md com diretrizes para role Designer
- Criação de template específico para role Designer
- Atualização de templates existentes com novas seções por role
- Documentação de critérios de opcionalidade para Designer e Arquiteto
- Guia de fluxos possíveis com diferentes combinações de roles opcionais

**Regra:** Qualquer alteração relevante neste material requer novo Canonical Cycle.

---

**Nota:** Este é material canônico - fonte única de verdade. Não será reinterpretado sem novo ciclo.
