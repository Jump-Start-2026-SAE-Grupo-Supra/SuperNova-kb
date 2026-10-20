# SuperNova KB

Base de conhecimento da **Equipe Supra** para o **Sebrae Supernova 2026 — 3a Temporada**.

## Estrutura

```
docs/
├── index.md                  # Página inicial
├── regulamento.md            # Regras e entregas
├── analise/                  # Análise de mercado
│   ├── ecossistema.md
│   ├── segmentos.md
│   └── investimentos.md
├── estrategia/               # Estratégia da equipe
│   ├── ganhadores.md
│   ├── avaliacao.md
│   └── ideias.md
└── documentos.md             # Fontes e PDFs
```

## Como rodar localmente

```bash
pip install mkdocs-material
mkdocs serve
```

O site abre em `http://localhost:8000`.

## Adicionando conteúdo

### Com a skill `/kb` (recomendado)

Este repo tem uma skill do [Claude Code](https://claude.com/claude-code) que guia a criação de páginas:

```bash
/kb
```

A skill pergunta o tipo de página, o conteúdo, a fonte e a seção, gera o rascunho no estilo da KB e apresenta para aprovação antes de salvar.

Aceita um argumento opcional para pular perguntas óbvias:

```bash
/kb relatório do Sebrae sobre ecossistema de startups 2024
```

**Marcador `>>`**: use antes de um trecho para o Claude expandir com mais profundidade.

```
Dados do censo. >>saúde tem pouco investimento mas muita presença
```

### Manualmente

Siga o fluxo descrito em [AI_USAGE.md](AI_USAGE.md).

## Convenção de commits

| Prefixo | Quando usar |
|:--------|:------------|
| `[ai]` | Conteúdo rascunhado por IA e editado por humano |
| `[ai-data]` | Dados extraídos/tabulados por IA a partir de fonte |
| *(sem prefixo)* | Conteúdo escrito 100% por humano |

## Deploy

Push na `main` dispara o deploy automático via GitHub Actions para GitHub Pages.

**Site:** https://jump-start-2026-sae-grupo-supra.github.io/SuperNova-kb/
