# AbacusSkills

Repositório de skills customizadas para o Abacus AI Agent.

## 📁 Estrutura do Repositório

```
AbacusSkills/
├── README.md                          # Este arquivo
├── skills/                            # Diretório raiz de todas as skills
│   ├── skill-name-1/                  # Cada skill tem sua própria pasta
│   │   ├── SKILL.md                   # Documentação principal da skill
│   │   ├── references/                # Arquivos de referência (opcional)
│   │   ├── scripts/                   # Scripts executáveis (opcional)
│   │   └── assets/                    # Recursos visuais/templates (opcional)
│   ├── skill-name-2/
│   │   └── SKILL.md
│   └── ...
└── docs/                              # Documentação geral (futuro)
```

## 🎯 Convenções de Organização

### Nomenclatura de Skills
- **Formato:** `verbo-substantivo` (ex: `creating-linkedin-image-prompts`, `analyzing-spreadsheets`)
- **Caracteres:** apenas letras minúsculas, números e hífens
- **Máximo:** 64 caracteres
- **Idioma:** inglês para o nome técnico (a descrição e conteúdo podem estar em qualquer idioma)

### Estrutura de Cada Skill
Cada skill deve conter:

1. **`SKILL.md`** (obrigatório) — arquivo principal com:
   - Frontmatter YAML com `name` e `description`
   - Visão geral da funcionalidade
   - Fluxo de trabalho / instruções de uso
   - Regras essenciais
   - Referências a outros arquivos

2. **`references/`** (opcional) — documentos de referência detalhados:
   - Guidelines, frameworks, templates
   - Arquivos > 100 linhas devem incluir um `## Contents` no início

3. **`scripts/`** (opcional) — código executável:
   - Scripts Python, Bash, etc.
   - Devem ser auto-contidos ou documentar dependências

4. **`assets/`** (opcional) — recursos estáticos:
   - Templates, logos, fontes
   - Imagens de exemplo

## 📚 Skills Disponíveis

### [creating-linkedin-image-prompts](./skills/creating-linkedin-image-prompts/)
Cria prompts de geração de imagens atraentes e profissionais a partir de conteúdo do LinkedIn (posts, artigos, ideias, dados), maximizando engajamento visual e relevância profissional.

- **Arquivos:** SKILL.md, prompt-framework.md, linkedin-visual-guidelines.md
- **Idioma:** Português Brasileiro
- **Tipo:** Geração de prompts visuais

---

## 🚀 Como Adicionar uma Nova Skill

1. **Crie a estrutura local:**
   ```bash
   mkdir -p skills/nova-skill/references
   ```

2. **Crie o `SKILL.md`** com frontmatter:
   ```markdown
   ---
   name: nova-skill
   description: Descrição clara do que a skill faz e quando usar.
   ---
   
   # Título da Skill
   ...
   ```

3. **Adicione arquivos de suporte** (se necessário):
   - `references/` para documentação detalhada
   - `scripts/` para código executável
   - `assets/` para recursos estáticos

4. **Teste localmente** (se aplicável)

5. **Crie um PR:**
   - Branch: `feature/adiciona-skill-[nome]`
   - Commit: `"Adiciona skill [nome]"`
   - Atualize este README.md adicionando a skill à lista

## 📖 Princípios de Design

- **Modularidade:** Cada skill é independente
- **Clareza:** Documentação clara e exemplos práticos
- **Reutilização:** Skills devem ser genéricas o suficiente para múltiplos casos
- **Manutenibilidade:** Evite duplicação entre skills
- **Contexto eficiente:** Mantenha SKILL.md < 500 linhas; use arquivos de referência para detalhes

## 🔗 Recursos

- [Documentação do Abacus AI Agent](https://abacus.ai)
- [Guia de Criação de Skills](./docs/skill-creation-guide.md) _(futuro)_

---

**Última atualização:** 17 de setembro de 2026
