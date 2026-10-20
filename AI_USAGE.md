# Uso de IA na SuperNova KB

Guia para a equipe padronizar como usamos IA ao criar e editar conteúdo nesta base de conhecimento.

## Regra geral

> **IA é ferramenta, não autora.** Todo conteúdo gerado por IA deve ser revisado, verificado e se necessario, editado por um humano antes de entrar na KB. Ninguém faz merge de texto que não leu e entendeu.

## Ferramentas

Qualquer ferramenta de IA pode ser usada. Basta declarar qual foi utilizada na mensagem de commit.

## Skill `/kb` — forma recomendada

Este repo tem uma skill do Claude Code que automatiza todo o fluxo abaixo. Para usar:

```bash
/kb
```

Ou com uma descrição rápida:

```bash
/kb dados do censo sobre startups no DF
```

A skill faz as perguntas necessárias, gera o rascunho no estilo da KB, apresenta para validação e salva o arquivo. Use `>>` antes de qualquer trecho para indicar que o Claude deve expandir aquele ponto.

> Exemplo: `Relatório do Sebrae. >>mostra que saúde tem pouco VC mas muita presença no ecossistema`

O Claude vai expandir "mostra que saúde tem pouco VC..." com dados e análise, mantendo o estilo conciso.

Veja o [README](README.md) para mais detalhes sobre a skill.

---

## Fluxo manual (sem a skill)

Se preferir usar outra ferramenta de IA ou criar a página manualmente, siga este fluxo:

### 1. Defina o tipo e o objetivo da página

Antes de usar a IA, identifique que tipo de página você está criando:

#### Página de contexto (adicionar conhecimento à base)

Estamos trazendo uma informação externa para dentro da KB. Antes de gerar o conteúdo, responda:

- **O que é?** — nome do documento, relatório, dado ou fonte
- **De onde veio?** — link, PDF, palestra, conversa
- **O que isso nos faz conhecer?** — qual insight novo a equipe ganha com isso
- **Muda algo no que já decidimos?** — se contradiz, reforça ou abre caminho para alguma ideia existente

> Exemplo: "Estou adicionando dados do Startups Report 2022–2023 do Sebrae. Veio do PDF oficial. Nos mostra que saúde tem pouco investimento VC mas alta presença no ecossistema — reforça que é um setor com espaço."

#### Página de análise ou estratégia (responder uma pergunta)

Estamos produzindo conhecimento próprio a partir do que já temos. Antes de gerar, escreva a pergunta que a página precisa responder.

> Exemplo: "Quais são os critérios de avaliação do Supernova e o que pesa mais na nota?"

### 2. Forneça contexto à IA

Passe como entrada:

- O objetivo da página
- Dados brutos (trechos de PDFs, links, anotações)
- O estilo das páginas existentes (conciso, sem enrolação, com tabelas)

Exemplo de prompt:

```
Com base nestes dados do regulamento [colar trecho], crie uma página
em Markdown para o MkDocs Material. Estilo: direto, tabelas quando
possível, sem parágrafos genéricos. Use admonitions do MkDocs (!!! tip, 
!!! warning) quando relevante.
```

### 3. Revise e edite o resultado

Antes de adicionar à KB, confira:

- [ ] **Fatos corretos?** — compare com a fonte original (PDF, site)
- [ ] **Sem filler?** — remova frases genéricas tipo "é importante ressaltar que..."
- [ ] **Estilo consistente?** — headers com `##`, tabelas para comparações, admonitions para destaques
- [ ] **Fontes citadas?** — dados precisam de origem (página do PDF, link)
- [ ] **Sem opinião disfarçada de fato?** — IA tende a afirmar coisas sem base

### 4. Declare o uso de IA no commit

Use esta convenção de commit:

```
[ai] Adiciona página sobre critérios de avaliação

- Rascunho gerado com Claude, revisado e editado manualmente
- Fonte: Regulamento Sebrae Supernova (p. 12-15)
```

Prefixos:

| Prefixo | Quando usar |
|:--------|:------------|
| `[ai]` | Conteúdo rascunhado por IA e editado por humano |
| `[ai-data]` | Dados extraídos/tabulados por IA a partir de fonte |
| *(sem prefixo)* | Conteúdo escrito 100% por humano |

## Padrão de estilo da KB

Para manter consistência entre páginas (com ou sem IA):

### Estrutura

```markdown
# Título da Página

Parágrafo curto de contexto (1-2 frases).

## Seção principal

Conteúdo direto. Tabelas para comparações.

| Coluna A | Coluna B |
|:---------|:---------|
| dado     | dado     |

!!! tip "Destaque relevante"
    Texto curto do destaque.

## Outra seção

Mais conteúdo.
```

### Regras de estilo

1. **Concisão** — se pode ser uma tabela, faça uma tabela
2. **Sem enrolação** — primeira frase já entrega informação
3. **Headers hierárquicos** — `#` só no título, `##` para seções, `###` para subseções
4. **Admonitions** — `!!! tip` para dicas, `!!! warning` para alertas, `!!! info` para contexto
5. **Links internos** — referencie outras páginas da KB com caminhos relativos
6. **Dados com fonte** — cite o documento/página de onde veio

### O que evitar

- Parágrafos longos explicando o óbvio
- "É importante destacar que..." / "Vale ressaltar que..." / "Nesse contexto..."
- Listas com 10+ itens sem agrupamento
- Duplicar informação que já está em outra página (linke)

## Declaração para o Sebrae

O regulamento do Supernova exige declarar uso de IA. Nossa declaração:

> A Equipe Supra utilizou ferramentas de inteligência artificial (Claude, ChatGPT) como auxílio na pesquisa, organização e síntese de informações públicas. Todo conteúdo foi revisado, verificado contra as fontes originais e editado pelos membros da equipe. A IA não foi usada para gerar a ideia de negócio em si, mas como ferramenta de produtividade na análise e documentação.

---

*Última atualização: 2026-10-20*
