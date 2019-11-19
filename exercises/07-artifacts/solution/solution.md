# Solution

In the job configuration, archive the artifact produced by the build. Check the box for generating fingerprints.

![Archive Artifacts](./images/archive-artifacts.png)

Execute the build and find the archived artifact.

![Archived Artifact](./images/build-artifact.png)

Have a look at the details of the fingerprinting.

![Fingerprint Details](./images/fingerprint-details.png)

Install the Copy Artifacts plugin from the Plugin Manager page.

![Copy Artifacts Plugin](./images/copy-artifacts-plugin.png)

Trigger the downstream job upon success.

![Trigger Downstream](./images/trigger-upstream.png)

Copy artifacts from the upstream job.

![Copy Artifact From Upstream](./images/copy-artifacts.png)

You can see the full usage of the artifact in upstream and downstream jobs.

![Fingerprint Usage](./images/fingerprints-upstream.png)