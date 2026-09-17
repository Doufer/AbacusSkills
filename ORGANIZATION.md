# Guia de Organização do Repositório AbacusSkills

## 🎯 Objetivo

Este documento explica como o repositório `AbacusSkills` está estruturado para suportar múltiplas skills de forma escalável, mantendo organização e facilidade de navegação.

## 📐 Arquitetura

### Estrutura de Diretórios

```
AbacusSkills/
│
├── skills/                           # Container principal
│   │
│   ├── creating-linkedin-image-prompts/
│   │   ├── SKILL.md                  # Documentação principal
│   │   └── references/               # Referências detalhadas
│   │       ├── prompt-framework.md
│   │       └── linkedin-visual-guidelines.md
│   │
│   ├── analyzing-sales-data/         # Exemplo: Skill futura
│   │   ├── SKILL.md
│   │   ├── scripts/
│   │   │   ├── analyze.py
│   │   │   └── export.py
│   │   └── references/
│   │       └── metrics-guide.md
│   │
│   ├── generating-marketing-copy/    # Exemplo: Skill futura
│   │   ├── SKILL.md
│   │   ├── assets/
│   │   │   └── tone-templates.json
│   │   └── references/
│   │       └── copywriting-frameworks.md
│   │
│   └── automating-report-creation/   # Exemplo: Skill futura
│       ├── SKILL.md
│       ├── scripts/
│       │   └── generate_report.py
│       ├── assets/
│       │   └── report-template.docx
│       └── references/
│           └── data-sources.md
│
├── docs/                             # Documentação geral (futuro)
│   ├── skill-creation-guide.md       # Como criar uma skill
│   ├── best-practices.md             # Melhores práticas
│   └── examples/                     # Exemplos de uso
│
├── .github/                          # Configurações do GitHub (futuro)
│   └── PULL_REQUEST_TEMPLATE.md      # Template para PRs
│
├── README.md                         # Documentação principal
└── ORGANIZATION.md                   # Este arquivo
```

## 🗂️ Categorização de Skills

À medida que o repositório cresce, você pode organizar skills por categorias:

### Opção 1: Flat Structure (atual, recomendado para < 20 skills)
```
skills/
  ├── skill-1/
  ├── skill-2/
  └── skill-3/
```
✅ **Vantagens:** Simples, fácil de navegar
❌ **Desvantagens:** Pode ficar confuso com muitas skills

### Opção 2: Categorized Structure (recomendado para > 20 skills)
```
skills/
  ├── content-creation/
  │   ├── creating-linkedin-image-prompts/
  │   ├── writing-blog-posts/
  │   └── generating-social-media-copy/
  ├── data-analysis/
  │   ├── analyzing-sales-data/
  │   └── visualizing-metrics/
  └── automation/
      ├── automating-reports/
      └── scheduling-tasks/
```
✅ **Vantagens:** Escalável, organizado por domínio
❌ **Desvantagens:** Camada extra de navegação

## 📋 Padrões de Nomenclatura

### Skills
- **Formato:** `verbo-gerúndio-objeto` ou `verbo-infinitivo-objeto`
- **Exemplos bons:** `creating-linkedin-image-prompts`, `analyzing-spreadsheets`, `writing-documentation`
- **Exemplos ruins:** `linkedinHelper`, `skill_1`, `utils`

### Arquivos de Referência
- **Formato:** `topico-tipo.md`
- **Exemplos:** `prompt-framework.md`, `api-reference.md`, `data-schemas.md`

### Scripts
- **Formato:** `verbo_acao.py` ou `verbo_acao.sh`
- **Exemplos:** `analyze_data.py`, `export_results.sh`, `validate_input.py`

## 🔄 Fluxo de Adição de Skills

```mermaid
graph LR
    A[Criar Skill Localmente] --> B[Testar no Abacus AI]
    B --> C[Criar Branch Feature]
    C --> D[Adicionar ao Repositório]
    D --> E[Atualizar README.md]
    E --> F[Criar Pull Request]
    F --> G[Revisar e Merge]
```

### Passo a Passo Detalhado

1. **Desenvolvimento Local**
   - Crie a skill em `/home/ubuntu/skills/` no ambiente do Abacus AI
   - Teste a funcionalidade completamente

2. **Preparação do Repositório**
   ```bash
   cd /home/ubuntu/github_repos/AbacusSkills
   git checkout main
   git pull origin main
   git checkout -b feature/adiciona-skill-[nome]
   ```

3. **Cópia de Arquivos**
   ```bash
   cp -r /home/ubuntu/skills/[nome]/ ./skills/
   ```

4. **Atualização da Documentação**
   - Adicione entrada em `README.md` na seção "Skills Disponíveis"
   - Mantenha ordem alfabética

5. **Commit e Push**
   ```bash
   git add skills/[nome]/ README.md
   git commit -m "Adiciona skill [nome]"
   git push origin feature/adiciona-skill-[nome]
   ```

6. **Pull Request**
   - Título: `Adiciona skill: [nome]`
   - Descrição: Explicar o que a skill faz e casos de uso

## 🏷️ Sistema de Tags (Futuro)

Adicionar metadata ao frontmatter para facilitar descoberta:

```yaml
---
name: creating-linkedin-image-prompts
description: Cria prompts de imagens...
tags:
  - content-creation
  - linkedin
  - image-generation
  - marketing
category: content-creation
language: pt-br
version: 1.0.0
author: Seu Nome
created: 2026-09-17
---
```

## 📊 Métricas de Qualidade

Para cada skill, considere documentar:

- **Complexidade:** Simples / Média / Avançada
- **Dependências:** Lista de ferramentas/APIs necessárias
- **Tempo médio de execução**
- **Taxa de sucesso** (se aplicável)

## 🔒 Controle de Versão

Quando uma skill sofre mudanças significativas:

1. **Breaking changes:** Incrementar versão principal (1.0 → 2.0)
2. **Novas features:** Incrementar versão menor (1.0 → 1.1)
3. **Bug fixes:** Incrementar patch (1.0.0 → 1.0.1)

Manter um `CHANGELOG.md` por skill (opcional):
```
skills/
  └── creating-linkedin-image-prompts/
      ├── SKILL.md
      ├── CHANGELOG.md
      └── references/
```

## 🤝 Colaboração

### Para Contribuidores

1. Cada skill deve ter um único propósito claro
2. Evite duplicação de funcionalidades
3. Documente exemplos de uso
4. Inclua tratamento de erros nos scripts
5. Teste antes de submeter PR

### Para Revisores de PR

Verificar:
- [ ] `SKILL.md` tem frontmatter correto
- [ ] Nome segue convenção de nomenclatura
- [ ] Documentação é clara e completa
- [ ] `README.md` foi atualizado
- [ ] Não há arquivos desnecessários (logs, temp, cache)
- [ ] Scripts têm shebang e são executáveis

## 🎓 Exemplos de Organização por Tamanho

### Repositório Pequeno (1-10 skills)
```
skills/
  ├── skill-a/
  ├── skill-b/
  └── skill-c/
```

### Repositório Médio (10-50 skills)
```
skills/
  ├── content/
  ├── data/
  ├── automation/
  └── utility/
```

### Repositório Grande (50+ skills)
```
skills/
  ├── content/
  │   ├── writing/
  │   ├── visual/
  │   └── audio/
  ├── data/
  │   ├── analysis/
  │   ├── visualization/
  │   └── transformation/
  └── automation/
      ├── social-media/
      ├── email/
      └── reporting/
```

---

**Próximos Passos Recomendados:**

1. ✅ Estrutura base criada
2. ⏳ Adicionar template de PR
3. ⏳ Criar guia de criação de skills
4. ⏳ Implementar sistema de tags
5. ⏳ Adicionar CI/CD para validação automática
