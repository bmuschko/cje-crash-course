# Exercise 11

In this exercise, you will set up a new multi-branch pipeline job and point it to an existing repository on GitHub. You will visualize the pipeline with the standard view and the Blue Ocean plugin.

## Creating a Pipeline Job

1. Have a look at the [repository](https://github.com/bmuschko/todo-spring-boot) `bmuschko/todo-spring-boot` on GitHub. The repository already contains the build definition in the form of a `Jenkinsfile`. Identify each of the steps.
2. In Jenkins, set up the credentials `SONARCLOUD_TOKEN` and `HEROKU_API_KEY` if they don't exist yet.
3. Create a new multi-branch pipeline job for the repository.
4. The initial build is triggered automatically. Have a look at the pipeline in the standard view and its console output.
5. Install the Blue Ocean plugin.
6. Open the Blue Ocean pipeline visualization for the job. Manually trigger the deployment step. Open a browser with the deployed application on Heroku.
7. Create a new branch named `bugfix` and push it to the remote repository. The code should be based off of `master`.
8. Select "Scan Multibranch Pipeline Now". The job should build the new branch.