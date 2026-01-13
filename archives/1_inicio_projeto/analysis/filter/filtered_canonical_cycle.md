# Canonical Cycle

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

## Definições dos Estágios

### 🧱 Raw Material

**Definição:** Dados brutos e não estruturados, coletados sem interpretação.

**Características:**
- Sem curadoria ou validação
- Nenhuma interpretação nem consenso
- Nenhuma verdade assumida

**Exemplos:**
- Anotações livres
- Atas de reunião
- Entrevistas e testemunhos de clientes
- Imagens, prints, áudios
- Arquivos diversos
- Observações informais

---

### 🔍 Filtered Material

**Definição:** Material interpretado e estruturado pela IA a partir do Raw Material e do objetivo do prompt.

**Características:**
- Resultado da interpretação da IA
- Baseado no Raw Material + objetivo do prompt + contexto da role
- Ainda não é oficial - é uma **proposta de entendimento**

**Pode conter:**
- Resumos estruturados
- Agrupamentos
- Levantamento de requisitos
- Hipóteses
- Riscos identificados
- Ambiguidades
- Suposições explícitas
- Pontos a confirmar

**Responsabilidade da IA:**
- Estruturar informações brutas
- Identificar padrões e relacionamentos
- Destacar ambiguidades e pontos de atenção
- Propor interpretações (não decidir verdade)

---

### 🏛️ Canonical Material

**Definição:** Material revisado, ajustado e aprovado por humano, tornando-se a fonte oficial de verdade para as próximas etapas.

**Características:**
- Validado conscientemente por humano
- Consistente e coerente
- Versionável
- Referenciável
- **Não reinterpretado sem novo ciclo**

**Regras:**
- ❌ Canonical Material não nasce da IA sozinho
- ✅ Requer aprovação humana explícita
- 🔁 Mudou o contexto? Novo ciclo
- 📌 Aqui a ambiguidade termina

**Responsabilidade do Humano:**
- Revisar o Filtered Material
- Ajustar e corrigir interpretações
- Aprovar como fonte de verdade
- Estabelecer o contrato para próximas etapas

---

### 📄 Artifacts

**Definição:** Representações formais de entregáveis reais, ainda não publicadas nos sistemas finais.

**Características:**
- Gerados a partir do Canonical Material
- Prontos para entrega
- Aguardando ação final de publicação

**Regras:**
- ❌ Nada gera artefato sem Canonical Material
- 📌 Artefatos sempre referenciam um Canonical

**Exemplos por Role:**

**Análise:**
- Tickets escritos (não criados no Jira)
- Requisitos estruturados
- Escopo definido

**Arquitetura:**
- Documentos de arquitetura
- Diagramas
- ADRs (Architecture Decision Records)

**Engenharia:**
- Planos técnicos
- Tarefas estruturadas
- Critérios de aceite

**Desenvolvimento:**
- Histórias de usuário
- Checklists de entrega
- Especificações técnicas

---

### 🚀 Delivery

**Definição:** Criação efetiva do artefato no sistema de destino e execução da entrega.

**Características:**
- Ação final do ciclo
- Publicação real nos sistemas
- Execução concreta

**Exemplos:**
- Criar ticket no Jira
- Abrir Pull Request
- Publicar documento
- Deploy
- Comunicação ao time

**Responsabilidade:** Role de Desenvolvimento (ou equivalente)

---

## Fluxo por Role

### 🧠 Role: Análise

```
Raw Material
 -> Filtered Material
   -> Canonical Material
     -> Analysis Artifacts
```

**Entrada:** Dados brutos sobre requisitos, necessidades, problemas
**Saída:** Tickets, requisitos, escopo validado

---

### 🏗️ Role: Arquitetura

```
Raw Material
 -> Filtered Material
   -> Canonical Material
     -> Architecture Artifacts
```

**Entrada:** Requisitos, constraints, contexto técnico
**Saída:** Diagramas, ADRs, decisões arquiteturais

---

### ⚙️ Role: Engenharia

```
Raw Material
 -> Filtered Material
   -> Canonical Material
     -> Engineering Artifacts
```

**Entrada:** Decisões arquiteturais, requisitos técnicos
**Saída:** Planos técnicos, tarefas, critérios de aceite

---

### 💻 Role: Desenvolvimento

```
Artifacts
 -> Delivery
```

**Entrada:** Artifacts de todas as roles anteriores
**Saída:** Entrega real (código, tickets criados, PRs abertos, etc.)

---

## Regras Implícitas do Canonical Cycle

### Regras de Validação

1. ❌ **Nada gera artefato sem Canonical Material**
   - Todo artefato deve ter um Canonical Material de origem
   - Não é permitido pular etapas

2. ❌ **Canonical Material não nasce da IA sozinho**
   - Sempre requer revisão e aprovação humana
   - IA propõe, humano decide

3. ✅ **Toda decisão tem um ponto humano explícito**
   - Cada transição `->` representa uma decisão humana
   - Não há automação de decisões críticas

4. 🔁 **Mudou o contexto? Novo ciclo**
   - Alterações relevantes invalidam o Canonical Material
   - Requer reinício do ciclo a partir do Raw Material ou Filtered Material

5. 📌 **Artefatos sempre referenciam um Canonical**
   - Rastreabilidade é obrigatória
   - Cada artefato deve indicar seu Canonical Material de origem

---

## Diretrizes para Agentes de IA

### Agente de Filtragem (Raw → Filtered)

**Responsabilidade:**
- Interpretar e estruturar Raw Material
- Identificar padrões e relacionamentos
- Destacar ambiguidades e pontos de atenção
- Propor hipóteses e suposições explícitas

**O que fazer:**
- ✅ Estruturar informações de forma clara
- ✅ Agrupar informações relacionadas
- ✅ Identificar contradições ou inconsistências
- ✅ Destacar pontos que precisam confirmação humana
- ✅ Propor interpretações baseadas em evidências

**O que NÃO fazer:**
- ❌ Assumir verdades sem evidência
- ❌ Decidir sobre ambiguidades
- ❌ Omitir informações importantes
- ❌ Criar informações que não estão no Raw Material
- ❌ Pular para conclusões sem destacar incertezas

**Formato de saída:**
- Estruturado e organizado
- Com seções claras
- Com destaque para ambiguidades
- Com suposições explícitas

---

### Agente de Geração de Artefatos (Canonical → Artifacts)

**Responsabilidade:**
- Gerar artefatos formais baseados no Canonical Material
- Garantir que artefatos referenciem o Canonical Material
- Formatar conforme padrões do sistema de destino

**O que fazer:**
- ✅ Usar apenas Canonical Material como fonte
- ✅ Referenciar o Canonical Material no artefato
- ✅ Seguir formatos e padrões estabelecidos
- ✅ Garantir consistência entre artefatos
- ✅ Preparar artefato para publicação (mas não publicar)

**O que NÃO fazer:**
- ❌ Usar Raw Material ou Filtered Material diretamente
- ❌ Criar artefatos sem Canonical Material válido
- ❌ Publicar artefatos automaticamente
- ❌ Modificar Canonical Material durante geração

**Formato de saída:**
- Artefato completo e pronto
- Referência ao Canonical Material
- Formato adequado para o sistema de destino
- Não publicado, apenas preparado

---

## Diretrizes para Humanos

### Revisor de Filtered Material

**Responsabilidade:**
- Revisar interpretações da IA
- Corrigir erros de interpretação
- Resolver ambiguidades
- Aprovar como Canonical Material

**Checklist:**
- [ ] Interpretações fazem sentido?
- [ ] Ambiguidades foram resolvidas?
- [ ] Informações estão completas?
- [ ] Suposições são válidas?
- [ ] Estou confortável em usar isso como verdade?

---

### Aprovador de Canonical Material

**Responsabilidade:**
- Estabelecer o Canonical Material como fonte de verdade
- Garantir que está completo e correto
- Versionar quando necessário

**Checklist:**
- [ ] Material está completo?
- [ ] Está correto e consistente?
- [ ] Posso usar como fonte única de verdade?
- [ ] Está versionado adequadamente?

---

## Versionamento

### Canonical Material

- Deve ser versionado quando aprovado
- Versões anteriores devem ser mantidas para rastreabilidade
- Mudanças significativas requerem novo ciclo

### Artefatos

- Devem referenciar versão específica do Canonical Material
- Histórico de geração deve ser mantido

---

## Estrutura de Diretórios Sugerida

```
projeto/
├── raw/              # Raw Material
├── filter/           # Filtered Material
├── canonical/        # Canonical Material
├── artifacts/        # Artifacts
│   ├── analysis/
│   ├── architecture/
│   ├── engineering/
│   └── development/
└── delivery/         # Logs e registros de delivery
```

---

## Objetivo do Repositório

Criar um repositório exemplo que:
- Demonstre o fluxo do Canonical Cycle
- Forneça templates e exemplos
- Inclua README explicativo
- Seja referência para novos projetos

**Componentes necessários:**
1. README.md explicando o Canonical Cycle
2. Exemplos de cada estágio (raw, filter, canonical, artifacts)
3. Templates para cada role
4. Diretrizes de uso
5. Estrutura de diretórios padrão
