# GHA Mobile Test

[![release][release-badge]][release]

The purpose of this GitHub Action is to automate the testing of mobile apps.

**NOTE:** This action expects that the repo will have been checked out prior to running the action.

## Usage

```yaml
name: Test-Lint

pull_request:
  types: [opened, synchronize, reopened]

jobs:
  test:
    name: Type-Check, Test, and Lint
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2
        with:
          submodules: true
      - name: Test App
        uses: dmsi-io/gha-mobile-test@main
```

## Inputs

| NAME               | DESCRIPTION                                                                                                              | TYPE      | REQUIRED | DEFAULT |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------ | --------- | -------- | ------- |
| `typescript`       | Allows enabling/disabling the TypeScript type checker (runs without emitting). Expects `yarn tsc` to be a valid command. | `boolean` | `false`  | `true`  |
| `test`             | Allows enabling/disabling unit test. Expects `yarn test` to be a valid command.                                          | `boolean` | `false`  | `true`  |
| `lint`             | Allows enabling/disabling the linter. Expects `yarn lint` to be a valid command.                                         | `string`  | `false`  | `true`  |
| `changelog`        | Checks for a valid entry to the changelog                                                                                | `boolean` | `false`  | `false` |
| `GHA_ACCESS_TOKEN` | The GitHub access token to use for authentication.                                                                       | `string`  | `false`  | `''`    |
| `GHA_ACCESS_USER`  | The GitHub access user to use for authentication.                                                                        | `string`  | `false`  | `''`    |
| `JIRA_BASE_URL`    | The Jira base URL used for creating links to Jira issues.                                                                | `string`  | `false`  | `''`    |

<!-- badge links -->

[release]: https://github.com/dmsi-io/gha-mobile-test/releases
[release-badge]: https://img.shields.io/github/v/release/dmsi-io/gha-mobile-test?style=for-the-badge&logo=github
