# Exercise 14

In this exercise, you'll take the existing pipeline definition from the previous exercise and turn it into a reusable shared library.

## Writing and Using a Shared Library

1. Set up a new GitHub repository named `jenkins-standard-go-pipeline`. It will define a standard pipeline definition for Go projects implemented as shared library.
2. Add the file `vars/standard.groovy` that defines the declarative pipeline as global variable. Make the Go tool name and golang-ci version configurable with the help of parameters.
3. Push the changes to the `master` branch and configure the shared library in Jenkins.
4. Configure the shared library for consumption in Jenkins with the name `go-pipeline`.
5. Set up a new GitHub repository named `go-project-by-template`. Initialize a new Go project by running `go mod init github.com/bmuschko/hello-world` and adding a simple `main.go` file.
6. Add a new `Jenkinsfile`. Consume the shared library and call the global variable.
7. Trigger a build and visualize the pipeline in Jenkins.