# Recognize CLI Action

With this action, `recognize-cli` commands can be executed. The `recognize-cli` can be used to check project policy versions
against the most up-to-date versions.

## Example
```yaml
on:
  push:
    branches: [develop]
jobs:
  security-report:
    runs-on: ubuntu-latest
    steps:
      - uses: recognizegroup/recognize-cli-action@v1
        with:
          application-insights-key: ${{ secrets.RECOGNIZE_CLI_APPLICATION_INSIGHTS_KEY }}  # (required) Key for communication with the application insights instance
          command: policies validate                                                       # (optional) Specify custom command to execute
          version: v1.0.0                                                                  # (optional) Install a specific version of the CLI
```
