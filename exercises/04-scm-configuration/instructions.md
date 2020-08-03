# Exercise 4

In this exercise, you will create a new job that pulls the source code from a [repository on GitHub](https://github.com/bmuschko/gradle-initializr) named Gradle Initializr. Upon triggering a build, the job will execute a Gradle build.

## Configuring a GitHub Repository

1. Create a new freestyle job named `gradle-initializr`.
2. Configure Git as the SCM and use the repository URL `https://github.com/bmuschko/gradle-initializr.git`. Only build from the branch `master`.
3. Add a build step "Invoke Gradle script" to run the Gradle command `clean build` using the Wrapper.
4. Trigger a build and look at the output.