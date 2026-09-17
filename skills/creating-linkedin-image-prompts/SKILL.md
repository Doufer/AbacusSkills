---
name: creating-linkedin-image-prompts
description: Cria prompts de geração de imagens atraentes e profissionais a partir de conteúdo do LinkedIn (posts, artigos, ideias, dados), maximizando engajamento visual e relevância profissional. Use quando o usuário quiser transformar conteúdo do LinkedIn em imagens, gerar visuais para publicações profissionais, ou pedir direção visual para posts da rede.
---

# Criando Prompts de Imagens para LinkedIn

## Visão Geral
Esta skill converte conteúdo do LinkedIn (texto de posts, artigos, ideias, dados) em prompts de geração de imagens de alta qualidade, projetados para maximizar o engajamento visual e a relevância profissional. O produto final é um prompt estruturado, pronto para uso em ferramentas de geração de imagem (DALL-E, Midjourney, Stable Diffusion, Firefly, etc.).

## Fluxo de Trabalho
1. **Analisar o conteúdo** — leia o conteúdo do LinkedIn e extraia: mensagem central, tom, público-alvo, setor e chamada para ação (CTA).
2. **Escolher o conceito visual** — selecione o tipo de visual que melhor comunica a mensagem: metáfora visual, visualização de dados, citação em destaque, cena profissional, comparação, etc.
3. **Definir o formato** — determine a proporção e as dimensões conforme o tipo de post (ver `references/linkedin-visual-guidelines.md`).
4. **Construir o prompt** — monte o prompt com o framework estruturado em `references/prompt-framework.md`.
5. **Validar** — confira o prompt contra os princípios de engajamento e as regras de texto em `references/linkedin-visual-guidelines.md`.

## Regras Essenciais
- Texto mínimo na imagem (respeitar a regra dos 20% do LinkedIn).
- Tom profissional e coerente com o setor do autor.
- Um único ponto focal claro por imagem.
- Paleta de cores consistente com a identidade do autor.
- O prompt descreve o RESULTADO visual desejado, não a ferramenta de geração.
- Sempre entregar o prompt no idioma do conteúdo original.

## Arquivos de Referência
- `references/prompt-framework.md` — framework completo de construção de prompts, com templates por tipo de visual e exemplos prontos.
- `references/linkedin-visual-guidelines.md` — especificações de imagem do LinkedIn, princípios de engajamento, regras de texto e estilos por setor.
