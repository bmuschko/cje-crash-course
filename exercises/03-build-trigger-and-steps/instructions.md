# Exercise 3

In this exercise, you will configure the job to build based on a cron definition. Moreover, you will create downstream job that should be built automatically if the upstream job is successful.

## Configuring Build Triggers and Steps for a Job

1. Add a default value for the build parameter named `MESSAGE` e.g. `Hello World!`.
2. Create a build trigger that builds the project every minute.
3. Add a build step that executes the shell command `echo "Message: $MESSAGE"`. The message is value of the parameter. On Windows, you have to execute a Windows batch command.
4. After a minute the first execution should have been triggered. Check the log output of the build and find the rendered message.
5. Create another freestyle project named `downstream-job` in the same folder.
6. Configure the initial job to execute the `downstream-job` if it was stable.