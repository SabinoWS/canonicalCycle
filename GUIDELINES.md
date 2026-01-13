# Diretrizes para Humanos

**Referência Canonical:** `archives/2_primeiras_melhorias/canonical/1_canonical_melhorias.md` v1.0

---

## Visão Geral

Este documento fornece diretrizes e checklists para humanos que participam do Canonical Cycle. Existem dois papéis principais:

1. **Revisor de Filtered Material** - transforma Filtered em Canonical
2. **Aprovador de Canonical Material** - valida e versiona o Canonical

---

## Revisor de Filtered Material

### Responsabilidade

Revisar o Filtered Material gerado pela IA, corrigir interpretações, resolver ambiguidades e aprovar como Canonical Material.

### Processo

1. **Receber Filtered Material** do Agente de Filtragem
2. **Revisar interpretações** da IA
3. **Corrigir erros** de interpretação
4. **Resolver ambiguidades** destacadas pela IA
5. **Ajustar e completar** informações quando necessário
6. **Aprovar como Canonical Material**

### Checklist de Revisão

Antes de aprovar como Canonical Material, verifique:

- [ ] **Interpretações fazem sentido?**
  - As interpretações da IA estão corretas?
  - Há erros de entendimento que precisam correção?

- [ ] **Ambiguidades foram resolvidas?**
  - Todas as ambiguidades destacadas pela IA foram esclarecidas?
  - Não há mais pontos de incerteza?

- [ ] **Informações estão completas?**
  - O material contém todas as informações necessárias?
  - Faltam dados importantes do Raw Material?

- [ ] **Suposições são válidas?**
  - As suposições explícitas da IA são corretas?
  - Há suposições implícitas que precisam ser documentadas?

- [ ] **Estou confortável em usar isso como verdade?**
  - Posso confiar neste material como fonte única de verdade?
  - Está pronto para gerar artefatos?

### Ações Comuns

**Se encontrar erro de interpretação:**
- Corrija diretamente no material
- Documente a correção

**Se houver ambiguidade:**
- Resolva consultando Raw Material original
- Ou solicite mais informações
- Documente a decisão tomada

**Se faltar informação:**
- Complete com conhecimento disponível
- Ou retorne ao Raw Material para coletar mais dados

**Se suposição estiver incorreta:**
- Corrija a suposição
- Documente a suposição correta

### Formato do Canonical Material

Ao aprovar, o Canonical Material deve incluir:

1. **Cabeçalho de Aprovação**
   - Data de aprovação
   - Versão (ex: v1.0)
   - Aprovador
   - Referência ao Filtered Material original

2. **Conteúdo Validado**
   - Material revisado e corrigido
   - Ambiguidades resolvidas
   - Suposições validadas

3. **Metadados**
   - Status: "Aprovado como Canonical"
   - Pronto para geração de artefatos

---

## Aprovador de Canonical Material

### Responsabilidade

Estabelecer o Canonical Material como fonte oficial de verdade, garantir completude e versionar adequadamente.

### Processo

1. **Receber Canonical Material** do Revisor
2. **Validar completude** e correção
3. **Versionar** o material
4. **Estabelecer como fonte de verdade**
5. **Disponibilizar** para geração de artefatos

### Checklist de Aprovação

Antes de estabelecer como fonte de verdade:

- [ ] **Material está completo?**
  - Contém todas as informações necessárias?
  - Não há lacunas importantes?

- [ ] **Está correto e consistente?**
  - Informações estão corretas?
  - Não há contradições internas?
  - Consistente com contexto do projeto?

- [ ] **Posso usar como fonte única de verdade?**
  - Confio neste material completamente?
  - Outros podem usar sem dúvidas?

- [ ] **Está versionado adequadamente?**
  - Versão está clara e documentada?
  - Histórico de versões está mantido?

### Versionamento

**Formato de versão:** `v{major}.{minor}`

- **v1.0** - primeira versão aprovada
- **v1.1** - pequenas correções, sem mudança de contexto
- **v2.0** - mudanças significativas (novo ciclo)

**Quando criar nova versão:**
- Mudanças significativas no conteúdo
- Correções importantes
- Atualizações de contexto

**Quando iniciar novo ciclo:**
- Mudança de contexto relevante
- Invalidação do Canonical atual
- Necessidade de reprocessar desde o Raw Material

---

## Boas Práticas

### Para Revisores

1. **Seja rigoroso na revisão**
   - Não aceite ambiguidades não resolvidas
   - Não deixe suposições implícitas

2. **Documente decisões**
   - Quando resolver ambiguidade, documente o motivo
   - Quando corrigir interpretação, explique a correção

3. **Mantenha rastreabilidade**
   - Sempre referencie o Filtered Material original
   - Mantenha histórico de mudanças

### Para Aprovadores

1. **Valide completamente antes de aprovar**
   - Não aprove material incompleto
   - Garanta que está pronto para uso

2. **Versionamento consistente**
   - Use sistema de versionamento claro
   - Mantenha histórico de versões

3. **Comunicação clara**
   - Documente quando material é aprovado
   - Informe quando novo ciclo é necessário

---

## Quando Iniciar Novo Ciclo

Inicie um novo Canonical Cycle quando:

- ✅ **Mudança de contexto relevante**
  - Novos requisitos
  - Mudança de escopo
  - Alteração de constraints

- ✅ **Canonical Material inválido**
  - Erro descoberto que invalida o material
  - Informação incorreta que afeta todo o material

- ✅ **Necessidade de reprocessar**
  - Raw Material foi atualizado significativamente
  - Nova informação que muda interpretação

**NÃO inicie novo ciclo para:**
- Pequenas correções (use nova versão)
- Atualizações menores (use nova versão)
- Clarificações pontuais (use nova versão)

---

## Fluxo de Decisão

```
Filtered Material recebido
    ↓
Revisar com checklist
    ↓
Há problemas?
    ├─ SIM → Corrigir → Revisar novamente
    └─ NÃO → Aprovar como Canonical Material
                ↓
            Versionar
                ↓
            Estabelecer como fonte de verdade
                ↓
            Disponibilizar para artefatos
```

---

## Exemplos

### Exemplo 1: Revisão Bem Sucedida

**Filtered Material:** Requisitos estruturados com 2 ambiguidades destacadas
**Ação do Revisor:** Resolve ambiguidades consultando cliente, corrige 1 interpretação
**Resultado:** Canonical Material v1.0 aprovado

### Exemplo 2: Necessidade de Novo Ciclo

**Canonical Material:** Requisitos aprovados v1.0
**Mudança:** Cliente alterou escopo do projeto significativamente
**Ação:** Iniciar novo ciclo desde Raw Material atualizado

---

---

## Diretrizes por Role

### 🧠 Revisor/Aprovador - Role: Análise

**Responsabilidades:**
- Revisar Filtered Material com foco em requisitos e análise de negócio
- Validar que requisitos estão completos e corretos
- Aprovar Canonical Material que será usado para gerar épicos e histórias

**Checklist específico:**
- [ ] Requisitos funcionais estão claros?
- [ ] Requisitos não funcionais foram identificados?
- [ ] Épicos e histórias propostas fazem sentido?
- [ ] Ambiguidades sobre escopo foram resolvidas?
- [ ] Análise de negócio está completa?

---

### 🏗️ Revisor/Aprovador - Role: Arquitetura

**Responsabilidades:**
- Revisar Filtered Material com foco em decisões arquiteturais
- Validar que decisões técnicas estão fundamentadas
- Aprovar Canonical Material que será usado para gerar ADRs e diagramas

**Quando esta role é necessária:**
- ✅ Decisões arquiteturais significativas
- ✅ Mudanças estruturais no sistema
- ✅ Necessidade de definir padrões técnicos
- ❌ Correções simples (pode ser pulada)
- ❌ Ajustes pontuais (pode ser pulada)
- ❌ Decisões arquiteturais já estabelecidas (pode ser pulada)

**Checklist específico:**
- [ ] Decisões arquiteturais estão fundamentadas?
- [ ] Alternativas foram consideradas?
- [ ] Trade-offs foram analisados?
- [ ] Padrões técnicos estão claros?
- [ ] Impactos arquiteturais foram identificados?

---

### ⚙️ Revisor/Aprovador - Role: Engenharia

**Responsabilidades:**
- Revisar Filtered Material com foco em análise técnica
- Validar que tasks estão detalhadas e viáveis
- Aprovar Canonical Material que será usado para implementação

**Checklist específico:**
- [ ] Análise de impactos está correta?
- [ ] Esforço estimado é realista?
- [ ] Localização das mudanças no código está clara?
- [ ] Tasks estão detalhadas o suficiente?
- [ ] Dependências foram identificadas?

---

### 💻 Revisor/Aprovador - Role: Desenvolvimento

**Responsabilidades:**
- Revisar código gerado/modificado (Filtered Material)
- Validar que código segue padrões do projeto
- Aprovar código staged no git (Canonical Material)

**Checklist específico:**
- [ ] Código segue padrões do projeto?
- [ ] Código está testável?
- [ ] Implementação está completa?
- [ ] Código está pronto para commit?

---

## Processo de Aprovação em Duas Etapas

**Processo aprovado:**

1. **Etapa 1: Filtered → Canonical**
   - Humano revisa e aprova o Filtered Material
   - Agente gera o Canonical Material automaticamente
   - Humano revisa e aprova o Canonical Material final

2. **Etapa 2: Canonical → Artifacts**
   - Canonical Material aprovado pode gerar artefatos a qualquer momento
   - Artefatos podem ser regenerados (são descartáveis)

**Importante:** Cada etapa requer aprovação humana explícita.

---

## Suporte

Para dúvidas sobre o processo:
- Consulte [README.md](./README.md) para visão geral
- Veja [examples/](./examples/) para exemplos práticos
- Use [templates/](./templates/) como referência de formato
- Consulte [AGENTS.md](./AGENTS.md) para entender como agentes trabalham
