# Artifacts - Repositório Canonical Cycle

**Referência Canonical:** `canonical_canonical_cycle.md` v1.0

---

## Lista de Artefatos a Gerar

### 📄 Documentação Principal

#### 1. README.md
**Descrição:** Documento principal do repositório explicando o Canonical Cycle
**Conteúdo:**
- Visão geral do Canonical Cycle
- Fluxo completo com diagrama
- Quick start / Como usar
- Estrutura do repositório
- Links para outros documentos
- Contribuindo

**Localização:** `/README.md`

---

#### 2. AGENTS.md
**Descrição:** Diretrizes detalhadas para agentes de IA
**Conteúdo:**
- Diretrizes para Agente de Filtragem (Raw → Filtered)
- Diretrizes para Agente de Geração de Artefatos (Canonical → Artifacts)
- Prompts padrão para cada tipo de agente
- Exemplos de uso
- Regras e restrições

**Localização:** `/AGENTS.md`

---

#### 3. GUIDELINES.md
**Descrição:** Diretrizes para humanos no processo
**Conteúdo:**
- Checklist para Revisor de Filtered Material
- Checklist para Aprovador de Canonical Material
- Boas práticas
- Quando iniciar novo ciclo
- Como versionar

**Localização:** `/GUIDELINES.md`

---

### 📁 Estrutura de Diretórios

#### 4. Estrutura Base
**Descrição:** Estrutura de diretórios padrão do Canonical Cycle
**Diretórios:**
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

**Artefato:** `.canonical-cycle-structure` ou `STRUCTURE.md`

---

### 📋 Templates

#### 5. Template: Raw Material
**Descrição:** Template para criar novos Raw Materials
**Arquivo:** `templates/raw-material-template.md`
**Conteúdo:**
- Estrutura padrão
- Seções sugeridas
- Exemplos de conteúdo

---

#### 6. Template: Filtered Material
**Descrição:** Template para Filtered Material
**Arquivo:** `templates/filtered-material-template.md`
**Conteúdo:**
- Estrutura esperada
- Seções obrigatórias (ambiguidades, suposições)
- Formato de saída

---

#### 7. Template: Canonical Material
**Descrição:** Template para Canonical Material
**Arquivo:** `templates/canonical-material-template.md`
**Conteúdo:**
- Estrutura de aprovação
- Campos de versionamento
- Referências

---

#### 8. Template: Artifacts
**Descrição:** Templates para diferentes tipos de artefatos
**Arquivos:**
- `templates/artifacts/analysis-artifact-template.md`
- `templates/artifacts/architecture-artifact-template.md`
- `templates/artifacts/engineering-artifact-template.md`
- `templates/artifacts/development-artifact-template.md`

---

### 📚 Exemplos

#### 9. Exemplo Completo: Fluxo de Análise
**Descrição:** Exemplo completo do ciclo para Role de Análise
**Diretório:** `examples/analysis-cycle/`
**Arquivos:**
- `raw/requisitos-cliente.md`
- `filter/filtered-requisitos.md`
- `canonical/canonical-requisitos.md`
- `artifacts/ticket-jira.md`

---

#### 10. Exemplo Completo: Fluxo de Arquitetura
**Descrição:** Exemplo completo do ciclo para Role de Arquitetura
**Diretório:** `examples/architecture-cycle/`
**Arquivos:**
- `raw/contexto-tecnico.md`
- `filter/filtered-decisoes.md`
- `canonical/canonical-arquitetura.md`
- `artifacts/adr-001.md`

---

#### 11. Exemplo Completo: Fluxo de Engenharia
**Descrição:** Exemplo completo do ciclo para Role de Engenharia
**Diretório:** `examples/engineering-cycle/`
**Arquivos:**
- `raw/requisitos-tecnicos.md`
- `filter/filtered-plano.md`
- `canonical/canonical-plano-tecnico.md`
- `artifacts/plano-implementacao.md`

---

### 🔧 Configuração e Ferramentas

#### 12. .canonical-cycle.yml
**Descrição:** Arquivo de configuração do Canonical Cycle
**Conteúdo:**
- Versão do ciclo
- Roles configuradas
- Diretórios padrão
- Regras de validação

**Localização:** `/.canonical-cycle.yml`

---

#### 13. .gitignore
**Descrição:** Gitignore específico para Canonical Cycle
**Conteúdo:**
- Ignorar arquivos temporários
- Manter estrutura mas ignorar conteúdo sensível se necessário

**Localização:** `/.gitignore` (ou seção no existente)

---

### 📖 Glossário e Referências

#### 14. GLOSSARY.md
**Descrição:** Glossário de termos do Canonical Cycle
**Conteúdo:**
- Definições de todos os termos
- Relacionamentos entre conceitos
- Referências cruzadas

**Localização:** `/GLOSSARY.md`

---

#### 15. CHANGELOG.md
**Descrição:** Histórico de mudanças do repositório
**Conteúdo:**
- Versões do Canonical Cycle
- Mudanças na metodologia
- Atualizações de templates

**Localização:** `/CHANGELOG.md`

---

### 🎯 Quick Reference

#### 16. QUICK-START.md
**Descrição:** Guia rápido para começar a usar
**Conteúdo:**
- Passos iniciais
- Exemplo mínimo
- Links rápidos

**Localização:** `/QUICK-START.md`

---

#### 17. WORKFLOW.md
**Descrição:** Diagrama de fluxo de trabalho visual
**Conteúdo:**
- Fluxograma do ciclo
- Decisões em cada etapa
- Quando usar cada role

**Localização:** `/WORKFLOW.md`

---

## Resumo por Prioridade

### 🔴 Prioridade Alta (MVP)
1. README.md
2. AGENTS.md
3. GUIDELINES.md
4. Estrutura de diretórios base
5. Template: Raw Material
6. Template: Filtered Material
7. Template: Canonical Material
8. Um exemplo completo (Análise)

### 🟡 Prioridade Média
9. Templates de Artifacts (todos os tipos)
10. Exemplos adicionais (Arquitetura, Engenharia)
11. GLOSSARY.md
12. QUICK-START.md
13. WORKFLOW.md

### 🟢 Prioridade Baixa (Nice to Have)
14. .canonical-cycle.yml
15. CHANGELOG.md
16. Ferramentas de validação
17. Scripts de automação

---

## Formato de Referência Canonical

Todos os artefatos devem incluir no topo:

```markdown
**Referência Canonical:** `canonical_canonical_cycle.md` v1.0
**Gerado em:** [data]
**Role:** [análise/arquitetura/engenharia/desenvolvimento]
```

---

## Checklist de Geração

Para cada artefato:
- [ ] Baseado no Canonical Material
- [ ] Referência ao Canonical incluída
- [ ] Formato adequado para o destino
- [ ] Pronto para publicação (mas não publicado)
- [ ] Revisado e consistente
