# Solution

We'll start by creating the new freestyle job.

![New Freestyle Job](./images/new-freestyle-job.png)

Configure the job as follows.

![Job Configuration](./images/job-configuration.png)

The build will ask for a parameter value when triggered.

![Build with Parameters](./images/build-with-params.png)

The build history only stores the previous two builds.

![Build History](./images/build-history.png)

Create a new view.

![New View](./images/new-view.png)

After adding the job to the view, it will show up in a separate tab.

![Job in View](./images/job-in-view.png)

Create a new folder.

![New Folder](./images/new-folder.png)

The job became a child of the folder after moving it there.

![Job In Folder](./images/job-in-folder.png)

Navigating to the `job` directory under the Jenkins Home reveals the build history.

```bash
$ cd /Users/bmuschko/.jenkins/jobs/freestyle/jobs
$ tree my-freestyle-job
my-freestyle-job
├── builds
│   ├── 1
│   │   ├── build.xml
│   │   ├── changelog.xml
│   │   └── log
│   ├── 2
│   │   ├── build.xml
│   │   ├── changelog.xml
│   │   └── log
│   ├── 3
│   │   ├── build.xml
│   │   ├── changelog.xml
│   │   └── log
│   ├── lastFailedBuild -> -1
│   ├── lastStableBuild -> 3
│   ├── lastSuccessfulBuild -> 3
│   ├── lastUnstableBuild -> -1
│   ├── lastUnsuccessfulBuild -> -1
│   └── legacyIds
├── config.xml
├── lastStable -> builds/lastStableBuild
├── lastSuccessful -> builds/lastSuccessfulBuild
└── nextBuildNumber

8 directories, 15 files
```