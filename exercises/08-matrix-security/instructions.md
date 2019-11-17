# Exercise 8

In this exercise, you'll create a new user and assign read permissions. You will verify permissions for the admin user and the new user by logging into Jenkins with the appropriate credentials.

## Creating a User and Setting Permissions

1. Ensure that you are logged in as admin user.
2. Create a new user named `miller`. Provide the relevant information.
3. Configure Matrix Security by adding the admin user and the newly created user. The admin user should have all permissions. The `miller` user should only have read permissions for jobs and views.
4. Log out of the system.
5. Log in with the user `miller` and navigate to one of the jobs. Notice that you cannot edit the configuration or trigger a new build.