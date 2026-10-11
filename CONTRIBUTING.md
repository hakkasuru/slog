# Contributing

You need the Go version set in `go.mod`, or newer.

## Before opening a pull request

From the repository root, run the static checks and the tests. Both commands must pass.

```shell
go vet ./...
go test ./...
```

The example tests in `example_test.go` send requests to a placeholder Slack webhook URL. Those requests can fail without failing the tests. The run can take several seconds while requests wait for the client timeout, and `-v` shows an `[ERROR]` line for each failed request.
