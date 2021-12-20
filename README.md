# gha-mobile-test

The purpose of this GitHub Action is to automate the testing of mobile apps.

### Usage

```yaml
name: Test-Lint

pull_request:
  types: [opened, synchronize, reopened]

jobs:
  test:
    name: Type-Check, Test, and Lint
    runs-on: ubuntu-latest
    steps:
      - name: Test App
        uses: dmsi-io/gha-mobile-test@main
        with:
          token: ${{ secrets.GHA_ACCESS_TOKEN }}
```

### Optional inputs

#### TypeScript

This value allows enabling/disabling the TypeScript type checker (runs without emitting). Expects `yarn tsc` to be a valid command.

Default: true

```yaml
  with:
    typescript: 'false'
```

#### Unit Tests

This value allows enabling/disabling unit test. Expects `yarn test` to be a valid command.

Default: true

```yaml
  with:
    test: 'false'
```

#### Linting

This value allows enabling/disabling the linter. Expects `yarn lint` to be a valid command.

Default: true

```yaml
  with:
    lint: 'false'
```
