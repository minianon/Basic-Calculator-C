# Basic Calculator in C: Low-Level Design

For the big picture see the [High-Level Design](hld.md).

## 1. Program flow

```mermaid
flowchart TB
  A[Read operator with scanf] --> B[Read num1 and num2 as float]
  B --> C{switch operator}
  C -->|+| D[print num1 + num2]
  C -->|-| E[print num1 - num2]
  C -->|*| F[print num1 * num2]
  C -->|/| G{num2 != 0?}
  G -->|yes| H[print num1 / num2]
  G -->|no| I["Error! Division by zero."]
  C -->|other| J["Invalid operator!"]
```

## 2. Data

| Variable | Type | Purpose |
|---|---|---|
| `operator` | `char` | One of `+ - * /` (read with `" %c"` to skip leftover whitespace) |
| `num1`, `num2` | `float` | Operands |

Results are printed as `%.2f`, e.g. `3.00 / 2.00 = 1.50`.
