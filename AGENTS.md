# Agents

Configurações de agentes de IA para este repositório.

## Skills disponíveis

### `/kb` — Adicionar conhecimento à base

**Arquivo:** `.claude/commands/kb.md`

Skill do Claude Code que padroniza a criação de páginas na KB. Guia o usuário por um fluxo estruturado:

1. **Coleta** — pergunta tipo de página (contexto ou análise), conteúdo, fonte e seção
2. **Contexto** — lê páginas existentes para manter estilo consistente
3. **Geração** — cria o rascunho em Markdown para MkDocs Material
4. **Validação** — apresenta o resultado para aprovação antes de salvar
5. **Salvamento** — cria o arquivo e atualiza o `mkdocs.yml`

#### Marcador `>>`

O usuário pode escrever respostas curtas e usar `>>` antes de trechos que o Claude deve expandir:

```
Dados do relatório Sebrae. >>mostra que saúde tem pouco VC mas alta presença
```

O Claude vai desenvolver o trecho marcado com dados e análise, sem perder o estilo conciso da KB.

#### Regras que a skill segue

- Estilo definido em [AI_USAGE.md](AI_USAGE.md)
- Sem filler, sem introduções genéricas
- Tabelas para comparações, admonitions para destaques
- Dados sempre com fonte
- Não faz commit — deixa para o usuário

## Padrões de uso de IA

Ver [AI_USAGE.md](AI_USAGE.md) para o guia completo de como a equipe usa IA neste repositório.
