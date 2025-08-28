# Changelog

All notable changes to the "language-mkq" extension.

## [1.1.0] - 2025-08-28
- SQL embedding refeito: 
  - Delimitadores ancorados por linha (`[SQL]` e `@>SQL`); término em `@>MKQ`, novo `[SQL]`, `##>` ou `]}`.
  - Inclusão real do grammar `source.sql` dentro do bloco.
  - Fallback SQL interno (keywords, tipos, strings, números, comentários, operadores) quando `source.sql` não estiver disponível.
- Correções de regex:
  - `format`: remove `|` e `^` indevidos no conjunto negado.
  - Lookahead de término para `]}` e `##>` corrigidos.
- Ativo o padrão `#numericos` no topo da grammar.
- Suporte de arquivo `.etq` adicionado ao `package.json` (já era suportado na grammar).
- Adicionada configuração `embeddedLanguages` para mapear `source.sql` → `sql`.

## [1.0.2] - 2023-??-??
- Fix README.md

## [1.0.0]
- Initial release
