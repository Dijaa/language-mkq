# Linguagem MKQ

Realce de sintaxe para a linguagem MKQ utilizada na OTM Suite.

## Funcionalidades
- Realce de sintaxe MKQ para `*.mkq`, `*.myo` e `*.etq`.
- Incorporação de SQL dentro de blocos MKQ, com regras internas de fallback caso a gramática SQL externa não esteja disponível.
- Realce de condicionais, parâmetros e delimitadores de formatação.


## Incorporação de SQL/PLI
Três formas de iniciar um bloco SQL/PLI (deve estar em linha própria):
- `[SQL]`
- `[PLI]`
- `@>SQL`


O bloco termina ao encontrar um dos seguintes delimitadores em linha própria:
- `@>MKQ` (ou qualquer outro `@>RPA|MKQ|MKPT|...`)
- `[SQL]` (novo bloco)
- `[PLI]` (novo bloco)
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
