# Exercise 2

In this exercise, you will create a new freestyle job and configure it to build with parameters. You'll also have a look at the Jenkins home directory to inspect the directory structure representing the job.

## Defining, Configuring and Organizing a Job

1. From the dashboard, click the "New Item" button.
2. Enter the item name `my-freestyle-job` and select "Freestyle project". Press the "OK" button.
3. In the job configuration, define the option to only keep the last 2 builds. Provide the description "A simple freestyle job". Upon building the project, a String parameter named `MESSAGE` should be provided. Press the "Save" button.
4. Trigger a new build by pressing the "Build with Parameters" button. Enter a value for the `MESSAGE` parameter. The build should finish successfully. Locate the provided parameter value in the build information.
5. Run the build three more times. What do you see?
6. Create a new view named `test`. Add the job to the view.
7. Create a new folder named `freestyle` as part of the view. Move the job into the folder.
8. Locate the build information in `$JENKINS_HOME`. Inspect the directory structure.