---
applyTo: "**/*.php"
---

## PHP Variable Naming Conventions

### Scalar values (int, string, etc.)
- Start with capital letter, use CamelCase: `$Id`, `$Price`, `$TotalCount`

### Arrays — mandatory prefixes
- `$lst*` — unordered list of homogeneous elements: `$lstElements`
- `$ul*` — ordered list: `$ulBreadcrumbs`
- `$dct*` — associative array of heterogeneous fields: `$dctElement`, `$dctFilter`
- `$ref*` — lookup/dictionary keyed by ID: `$refProducts`
- `$map*` — index map array where keys are data identifiers (e.g. product ID) and values are positional indexes into another array (e.g. a `$lst*` array containing that item): `$mapProductIdx[$ProductId]` → index in `$lstProducts`
- `$ar*` — arrays for native Bitrix component engine only: `$arFilter`, `$arResult`

### Objects
- Start with lowercase, use lowerCamelCase: `$catalogItem`
- `$rdb*` — iterable DB result: `$rdbPrices = \Bitrix\Catalog\Model\Price::getList($dctFilter);`

### Unused variable
- Always use `$_` for unused loop variables: `foreach ($ref as $Key => $_)`

## Comments
- Write all comments in Russian.
- Use `//` for regular inline comments.
- Use `#` prefix for actionable comments: `# TODO: добавить кэширование`,
  `# FIXME: ...`, `# NOTE: ...`
- Use `/** */` PHPDoc blocks for all function and method descriptions.

## Debugging
- Never use `var_dump()`. Use `\Kint::dump()` instead.

## Code style (PSR-12 based, with exceptions)

### General
- Prefer early return over deep nesting.

### Braces and blocks
- Use curly braces `{}` for all control structures containing PHP code.
- Use alternative syntax (`:` / `end*`) when the block contains HTML:
  `if ($Condition): ?> ... <?php endif;`
  `foreach ($lst as $Item): ?> ... <?php endforeach;`

### Spacing
- Add a space between function/method **name and `(`** in declarations:
  `function myMethod ($Arg)` — space required
  `myMethod($arg)` — no space on call