# Exercise 12

In this exercise, you'll create a declarative pipeline for a Go-based project. The `Jenkinsfile` will use some of the basic features of the pipeline DSL.

## Writing a Basic Jenkinsfile

1. Create a new GitHub repository named `go-on-jenkins`.
2. Create a new `Jenkinsfile` in the root directory of the repository as well as a simple `main.go` file. The main function just prints "Hello World!". The repository https://github.com/bmuschko/go-helloworld-template shows an example.
3. Commit the files and push them to the remote repository.
4. Set up a new pipeline job for this repository in Jenkins.
5. Install the [Jenkins Go plugin](https://plugins.jenkins.io/golang).
6. Configure the latest Go runtime as global tool. Use a name that reflects the Go version. Remember the name for the next step.
7. Enhance the `Jenkinsfile` based on the following requirements. The Jenkinsfile should use the declarative syntax.
    * The job can run on all agents.
    * The job sets the environment variable `GO111MODULES=on`.
    * The job uses the Go runtime from the global tool definition (see previous step).
    * The job specifies one build stage named "Build". The build stage executes the shell command `go build`.