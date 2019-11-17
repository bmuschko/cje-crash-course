# Solution

Configure the `master` node.

![Master Configuration](./images/master-config.png)

Add a new agent node.

![Agent Configuration](./images/agent-config.png)

You will see that the `master` node isn't even listed anymore in the executor overview.

![Node Overview](./images/node-overview.png)

Reconfigure the agent node to only build jobs with a specific label.

![Agent Label Configuration](./images/agent-label-config.png)

Reconfigure the job to only use agents that can handle a specific label.

![Job Label Configuration](./images/job-label-config.png)

A build of the job is now only handled by an agent with the assigned label.

![Build For Labeled Agent](./images/build-for-label.png)

Other jobs sit in a queue waiting for an agent that can handle the execution criteria.

![Build For Labeled Agent](./images/queued-job.png)