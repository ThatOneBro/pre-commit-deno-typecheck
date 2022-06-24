# pre-commit-deno-typecheck

[pre-commit](https://pre-commit.com/) git hooks for typechecking [Deno](https://deno.land/) projects.

## Reason to use this hook

Now that Deno (v1.23+) doesn't typecheck by default, you can potentially commit code that is not typesafe without knowing it. Use this hook if you prefer this typechecking to be forced pre-commit and you can make sure you don't miss any type errors.

## Using pre-commit-deno-typecheck with pre-commit

Add this to your `.pre-commit-config.yaml`

```yaml
- repo: https://github.com/ThatOneBro/pre-commit-deno-typecheck
  rev: v0.1.0 # Use the ref you want to point at
  hooks:
    - id: deno-typecheck
```

## Hooks available

### `deno-typecheck`

Typechecks all TypeScript files.

## Other recommended hooks

I recommend including the [pre-commit-deno](https://github.com/nozaq/pre-commit-deno) repo hooks by nozaq in your config, including `deno-fmt`, `deno-lint`, and `deno-test`. You can add all of these and the `deno-typecheck` to your pre-commit flow like this:

```yaml
- repo: https://github.com/ThatOneBro/pre-commit-deno-typecheck
  rev: v0.1.0 # Latest as of 24 Jun 2022
  hooks:
    - id: deno-typecheck
- repo: https://github.com/nozaq/pre-commit-deno
  rev: v0.1.0 # Latest as of 24 Jun 2022, use the ref you want
  hooks:
    - id: deno-fmt
    - id: deno-lint
    - id: deno-test
```