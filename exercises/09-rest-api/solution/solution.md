# Solution

Create the new user.

![Create User](./images/create-user.png)

Add user permissions.

![User Permissions](./images/user-permissions.png)

Generate the API token.

![API Token](./images/api-token.png)

Generate the Jenkins crumb from the CLI.

```bash
$ curl -u "buildbot:pwd" 'http://localhost:8080/crumbIssuer/api/xml?xpath=concat(//crumbRequestField,":",//crumb)'
Jenkins-Crumb:890d0b4c9c1b111deb55b196813a0ae1
$ export JENKINS_CRUMB=Jenkins-Crumb:890d0b4c9c1b111deb55b196813a0ae1
$ export JENKINS_API_TOKEN=11e2f3c68399b6bc3a28bc06e002be104d
```

Trigger a build with the `curl` command.

```bash
$ curl -X POST -H "$JENKINS_CRUMB" http://buildbot:$JENKINS_API_TOKEN@localhost:8080/job/gradle-initializr/build
```

Disable the job via the REST API. You will see that the job indicated its status.

```bash
$ curl -X POST -H "$JENKINS_CRUMB" http://buildbot:$JENKINS_API_TOKEN@localhost:8080/job/gradle-initializr/disable
```

![Disabled Job](./images/disabled-job.png)

Reenable the job.

```bash
$ curl -X POST -H "$JENKINS_CRUMB" http://buildbot:$JENKINS_API_TOKEN@localhost:8080/job/gradle-initializr/enable
```

Download the Jenkins URL by calling the URL `localhost:8080/jnlpJars/jenkins-cli.jar` from the browser.

In the terminal, navigate to the directory that contains the Jenkins CLI JAR file. Use the Jenkins CLI to trigger a build with the correct command. This simply provide the password instead of the API token.

```bash
$ java -jar jenkins-cli.jar -s http://localhost:8080 -auth buildbot:pwd build gradle-initializr
```