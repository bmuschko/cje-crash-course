# Exercise 10

You will start a VM using Vagrant as practice environment to set up a distributed build with 2 agents.

## Starting up the VMs

1. To start up the VMs, navigate to this directory. It should contain a `Vagrantfile`.
2. Run the command `vagrant up`. Bringing up the VMs might take some minutes. The two VMs will be available with the IP address `192.168.99.201` and `192.168.99.202`. The username/password credentials for those VMs are `jenkins:jenkins`.

## Configuring and Executing Jobs in a Distributed Build

1. Go to "Manage Jenkins" > "Manage Nodes". You should see a single `master` node.
2. Configure the `master` node by setting the # of executor value to 0. That will take care of never using the `master` for job workload.
3. Add new nodes by clicking "New Nodes". Enter an appropriate name and select the option "Permanent Agent". Use the remote directory `/home/jenkins/jenkins_slave` and set the # of executors to 2. Enter the IP address `192.168.99.201` as host and provide credentials by selecting "Username with password". You will likely have to create a new credential. To keep things easy select "Non verifying Verification Strategy".
4. Trigger a build. You should see that the build is only executed on the agent and not the `master` node.
5. Add one more agent with the IP address `192.168.99.202`.
6. Trigger a build. You should see that the build can be executed on any of the agents.
7. Configure one of the agents to only build jobs with a specific label e.g. `java`. Change the "Usage" field to "Only build jobs with label expressions matching this node".
8. Configure the `gradle-initializr` job and assign the label `java`.
9. Trigger a build of the `gradle-initializr` job. It is only executed by the dedicated agent.
10. Trigger other jobs that do not have the label `java` assigned to them. They are waiting for an agent that can execute the build.

## Shutting down the VMs

1. After you are done with the exercise, navigate to the directory containing the `Vagrantfile`.
2. Tear down the VM by executing `vagrant destroy -f`.