# Exercise 9

This exercise explores the use of the REST API to trigger a build for an existing job. You will configure security features as necessary.

## Using the REST API for Common Operations

1. Create a new user named `buildbot`.
2. Add adminstration permissions for the user.
3. Log in with user `buildbot`.
4. Generate the API token for the user.
5. Generate a Jenkins crumb from the command line.
6. Export the environment variables `JENKINS_CRUMB` and `JENKINS_API_TOKEN` with the correct values.
7. Trigger a build of the job `gradle-initializr` with a `curl` command using the REST API.
8. Disable the job `gradle-initializr` with a `curl` command using the REST API.
9. Reenable the job `gradle-initializr` with a `curl` command using the REST API.
10. Download the Jenkins CLI client.
11. Trigger the build of the job `gradle-initializr` with a `curl` command using the Jenkins CLI.