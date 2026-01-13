# Canonical Material - Requisitos do Cliente

**Versão:** v1.0
**Aprovado em:** 2024-01-16
**Aprovador:** Maria Santos
**Referência Filtered Material:** `filter/filtered-requisitos.md`
**Role:** Análise

---

## Status

✅ **Aprovado como Canonical Material**

Este material foi revisado, ajustado e aprovado como fonte oficial de verdade para as próximas etapas.

---

## Conteúdo Validado

### Requisitos Funcionais Aprovados

1. **Visualização de Pedidos em Tempo Real**
   - Sistema deve exibir pedidos atualizados em tempo real
   - Vendedores precisam ver status dos pedidos
   - Atualização automática sem necessidade de refresh manual

2. **Performance**
   - Sistema deve ter tempo de carregamento inferior a 2 segundos
   - Suportar pelo menos 100 usuários simultâneos

3. **Acesso Multiplataforma**
   - Sistema deve ser acessível via navegador web responsivo
   - Prioridade: Web responsivo (app nativo será avaliado em fase posterior)

4. **Relatórios de Vendas**
   - Relatórios básicos: vendas por período, vendas por vendedor
   - Formato: PDF e Excel
   - Dashboard básico com gráficos principais

### Requisitos Não Funcionais Aprovados

- Performance: tempo de resposta < 2 segundos
- Acessibilidade: web responsivo (mobile-first)
- Escalabilidade: suportar 100+ usuários simultâneos

---

## Decisões Tomadas Durante Revisão

### Decisão 1: Tipo de Aplicação Mobile
- **Ambiguidade original:** Cliente mencionou "funcionar no celular" sem especificar tipo
- **Decisão:** Iniciar com web responsivo (mobile-first), app nativo será avaliado posteriormente
- **Justificativa:** Reduz complexidade inicial, web responsivo atende necessidade imediata, permite validação antes de investir em app nativo

### Decisão 2: Tipos de Relatórios
- **Ambiguidade original:** "Relatórios de vendas" sem especificação
- **Decisão:** Iniciar com relatórios básicos (vendas por período, vendas por vendedor) em PDF/Excel, com dashboard básico
- **Justificativa:** Atende necessidade inicial, permite expansão futura baseada em feedback

### Decisão 3: Integração com Sistema Atual
- **Ambiguidade original:** Sistema atual não especificado, necessidade de integração não clara
- **Decisão:** Novo sistema será independente inicialmente, integração será avaliada em fase posterior
- **Justificativa:** Permite desenvolvimento sem dependências, integração pode ser adicionada após validação do sistema

### Decisão 4: Quantidade de Vendedores
- **Ambiguidade original:** "Muitos vendedores" sem quantidade específica
- **Decisão:** Dimensionar para 100 usuários simultâneos (estimativa conservadora)
- **Justificativa:** Permite desenvolvimento seguro, pode ser ajustado após validação com cliente

---

## Suposições Validadas

1. ✅ **Sistema atual existe e está em uso** - confirmado, mas não será integrado inicialmente
2. ✅ **Vendedores são usuários principais** - confirmado, sistema focado em vendedores
3. ✅ **Tempo real significa atualização automática** - confirmado, sem refresh manual
4. ✅ **Relatórios são para gestão/comercial** - confirmado, foco em vendas

---

## Correções Realizadas

- Adicionado requisito específico de performance (< 2 segundos)
- Especificado número de usuários simultâneos (100+)
- Definido escopo inicial de relatórios (básicos)
- Decisão sobre tipo mobile (web responsivo primeiro)

---

## Histórico de Versões

| Versão | Data | Aprovador | Mudanças |
|--------|------|-----------|----------|
| v1.0 | 2024-01-16 | Maria Santos | Versão inicial aprovada |

---

## Pronto para Geração de Artefatos

✅ Este Canonical Material está pronto para ser usado como fonte para geração de artefatos.

**Próximos artefatos sugeridos:**
- Ticket Jira com requisitos estruturados
- Documento de escopo do projeto
- Histórias de usuário iniciais

**Regra:** Qualquer alteração relevante neste material requer novo Canonical Cycle.

---

**Nota:** Este é material canônico - fonte única de verdade. Não será reinterpretado sem novo ciclo.
