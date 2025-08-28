# Language MKQ

Syntax highlighting for the MKQ language used in OTM Suite.

## Features
- MKQ syntax highlighting for `*.mkq`, `*.myo` and `*.etq`.
- SQL embedding inside MKQ blocks, with fallback SQL rules if the external SQL grammar is not available.
- Conditional, parameters and formatting delimiters highlighting.

## SQL Embedding
Two ways to start a SQL block (must be on its own line):
- `[SQL]`
- `@>SQL`

The SQL block ends when reaching one of the following on its own line:
- `@>MKQ` (ou qualquer outro `@>RPA|MKQ|MKPT|...`)
- `[SQL]` (novo bloco)
- `##>`
- `]}` (fechamento de parâmetro/format)

Exemplo:

```
-- isso é MKQ
[SQL]
select * from tabela where id = 10;
@>MKQ
texto normal mkq
```

Dica: use o comando “Developer: Reload Window” após instalar/atualizar a extensão. Para inspecionar escopos, use “Developer: Inspect Editor Tokens and Scopes”.

## Conhecidas / Limitações
- O fallback SQL cobre os principais keywords, tipos, strings, números, comentários e operadores. Quando a grammar oficial de `source.sql` estiver carregada, ela será usada automaticamente.
- Delimitadores de bloco SQL são ancorados por linha para reduzir falsos positivos. Se você precisa usar marcadores inline, abra uma issue com um exemplo real.

## Contribuir
Sugestões, bugs e melhorias são bem-vindos via issues/PRs.

## Changelog
Veja o arquivo `CHANGELOG.md`.
