# Solution

Modify the existing build parameter.

![String Parameter](./images/string-parameter.png)

Add the cron build trigger and the build step.

![Build Trigger And Step](./images/build-trigger-and-step.png)

The output render the interpolated value of the `echo` command.

```bash
Started by timer
Running as SYSTEM
Building in workspace /Users/bmuschko/.jenkins/workspace/freestyle/my-freestyle-job
[my-freestyle-job] $ /bin/sh -xe /var/folders/02/3dgzjkqj4kz0g7lnrk0w93c00000gn/T/jenkins3548490840940668236.sh
+ echo "Message: Hello World!"
Message: Hello World!
Finished: SUCCESS
```

Create a new job in the same folder.

![Both Jobs In Folder](./images/both-jobs-in-folder.png)

Configure the downstream job from the initial job.

![Downstream Job Configuration](./images/build-downstream.png)

The downstream job indicates the upstream job.

![Downstream Build Information](./images/executed-downstream-job.png)