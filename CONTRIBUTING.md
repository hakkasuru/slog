# Contributing

You need Go 1.18 or newer, the version set in `go.mod`.

## Before opening a pull request

Run these commands from the repository root. Both must exit with code 0.

1. Run the static checks:

   ```shell
   go vet ./...
   ```

2. Run the tests:

   ```shell
   go test ./...
   ```

The example tests in `example_test.go` send each message to a placeholder Slack webhook, so every request fails. Each request can wait up to the 1-second client timeout in `core/slack_core.go`, so the test run can take about 8 seconds. If you add `-v`, the output includes an `[ERROR]` line for each failed request. Those lines are expected, and the tests still pass.
