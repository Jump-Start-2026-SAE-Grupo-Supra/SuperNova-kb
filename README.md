# SuperNova KB

Base de conhecimento da **Equipe Supra** para o **Sebrae Supernova 2026 — 3a Temporada**.

## Estrutura

```
docs/
├── index.md                  # Página inicial
├── regulamento.md            # Regras e entregas
├── documentos.md             # Fontes e PDFs (visualização inline)
├── links.md                  # Links úteis
├── analise/                  # Análise de mercado
│   ├── ecossistema.md
│   ├── segmentos.md
│   └── investimentos.md
├── estrategia/               # Estratégia da equipe
│   ├── ganhadores.md
│   ├── avaliacao.md
│   └── ideias.md
└── assets/
    └── pdfs/                 # Documentos originais
        ├── regulamento.pdf
        └── startups-report-2022-2023.pdf
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

## Visualizando o site

O repo é privado, então o site roda localmente:

```bash
mkdocs serve
```

Acessa em `http://localhost:8000`. Atualiza automaticamente ao editar os arquivos.
