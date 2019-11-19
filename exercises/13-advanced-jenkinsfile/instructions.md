# Exercise 13

We'll want to enhance the existing Go pipeline by additional stages and implement a release workflow. The project is going to use an external tool called [GoReleaser](https://goreleaser.com/) to publish cross-compiled artifacts to [GitHub Releases](https://help.github.com/en/github/administering-a-repository/creating-releases). The binaries should only be released if the commit has been tagged. You will need to create an account on [CodeCov](https://codecov.io/) and set up a [GitHub token](https://github.com/settings/tokens) to follow along.

## Enhancing a Pipeline With Advanced Features

1. Add stage named `Test` that executes the Go `test` command.
    * Add a build step that runs the shell command `go test ./...`.
    * Generate code coverage metrics by adding the option `-coverprofile=coverage.txt` to the build step.
    * Publish the code coverage metrics to CodeCov by sending a curl command `curl -s https://codecov.io/bash | bash -s -`.
2. Add a stage named `Code Analysis` that uses [golangci-lint](https://github.com/golangci/golangci-lint) to detect issues with the code.
    * Add a build step for installing the `golangci-lint` with the shell command `curl -sfL https://install.goreleaser.com/github.com/golangci/golangci-lint.sh | bash -s -- -b $GOPATH/bin v1.18.0`
    * Add a build step that runs `golangci-lint` with the shell command `golangci-lint run`.
3. Add a stage named `Release` that uses [GoReleaser](https://github.com/goreleaser/goreleaser).
    * Only build this step if the commit has been tagged.
    * Set up a credential in Jenkins named `github_token` and set your [GitHub token](https://github.com/settings/tokens). Create a new token if you didn't set up one yet.
    * Retrieve the credential and set the value as environment variable named `GITHUB_TOKEN`.
    * Add a build step that runs the shell command `curl -sL https://git.io/goreleaser | bash`.