# Filtered Material - Requisitos do Cliente

**Referência Raw Material:** `raw/requisitos-cliente.md`
**Gerado em:** 2024-01-15
**Agente:** Agente de Filtragem - Análise
**Role:** Análise

---

## Resumo Executivo

Cliente solicita desenvolvimento de novo sistema de gestão de pedidos com foco em:
- Visualização de pedidos em tempo real
- Acesso para vendedores ao status de pedidos
- Melhoria de performance (sistema atual é lento)
- Acesso mobile/web
- Geração de relatórios de vendas

---

## Informações Estruturadas

### Requisitos Funcionais Identificados

1. **Visualização de Pedidos em Tempo Real**
   - Sistema deve exibir pedidos atualizados em tempo real
   - Vendedores precisam ver status dos pedidos

2. **Performance**
   - Sistema atual tem problemas de lentidão
   - Necessidade de melhorar tempo de carregamento

3. **Acesso Multiplataforma**
   - Necessidade de funcionar em dispositivos móveis
   - Não está claro se é app nativo ou web responsivo

4. **Relatórios**
   - Necessidade de relatórios de vendas
   - Tipos específicos de relatórios não foram detalhados

### Requisitos Não Funcionais Identificados

- Performance (tempo de resposta)
- Acessibilidade mobile

---

## Padrões Identificados

- Foco principal em **visibilidade** (pedidos em tempo real, status)
- Preocupação com **performance** (mencionado múltiplas vezes)
- Necessidade de **acesso remoto** (mobile, vendedores)

---

## Ambiguidades

> **IMPORTANTE:** Esta seção é obrigatória. Liste todas as ambiguidades encontradas.

### Ambiguidade 1: Tipo de Aplicação Mobile
- **Descrição:** Cliente mencionou "funcionar no celular" mas não especificou se é:
  - Aplicativo mobile nativo (iOS/Android)
  - Aplicativo web responsivo
  - Progressive Web App (PWA)
- **Contexto:** Requisito de acesso mobile
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 2: Tipos de Relatórios
- **Descrição:** Cliente mencionou "relatórios de vendas" mas não especificou:
  - Quais métricas devem ser incluídas
  - Periodicidade (diário, semanal, mensal)
  - Formato de saída (PDF, Excel, Dashboard)
- **Contexto:** Requisito de relatórios
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 3: Integração com Sistema Atual
- **Descrição:** Cliente mencionou "sistema atual" mas não especificou:
  - Qual é o sistema atual
  - Se precisa de integração/migração de dados
  - Se o sistema atual será substituído ou coexistirá
- **Contexto:** Mencionado indiretamente ao falar sobre performance
- **Necessita esclarecimento humano:** SIM

### Ambiguidade 4: Quantidade de Vendedores
- **Descrição:** Cliente mencionou "muitos vendedores" mas não especificou quantidade
- **Contexto:** Importante para dimensionamento e performance
- **Necessita esclarecimento humano:** SIM

---

## Suposições Explícitas

1. **Sistema atual existe e está em uso** - baseado na menção de "sistema atual"
2. **Vendedores são usuários principais do sistema** - baseado no foco em acesso para vendedores
3. **Tempo real significa atualização automática sem refresh manual** - interpretação padrão de "tempo real"
4. **Relatórios são para gestão/comercial** - baseado no contexto de "vendas"

---

## Pontos de Atenção

### Riscos Identificados
- **Risco de escopo não definido:** Múltiplas ambiguidades podem levar a expectativas não alinhadas
- **Risco de performance:** Sistema atual tem problemas, novo sistema precisa garantir melhorias

### Inconsistências
- Nenhuma inconsistência identificada no Raw Material

### Contradições
- Nenhuma contradição identificada no Raw Material

---

## Recomendações

1. **Agendar reunião de esclarecimento** para resolver ambiguidades antes de prosseguir
2. **Coletar informações sobre sistema atual** para entender contexto completo
3. **Definir escopo mínimo viável** considerando ambiguidades pendentes
4. **Priorizar requisitos de performance** dado o destaque no Raw Material

---

## Próximos Passos Sugeridos

1. Resolver ambiguidades listadas acima
2. Coletar email prometido pelo cliente
3. Revisar áudio da reunião para capturar detalhes adicionais
4. Validar suposições com cliente

---

**Status:** Proposta de entendimento - aguardando revisão humana para se tornar Canonical Material.
