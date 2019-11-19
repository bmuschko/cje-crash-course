# Exercise 7

You will enhance the existing job to generate a JAR file and store it on Jenkins. The job should record the MD5 hash for the artifact. Later, you will configure a downstream job that should be able to reuse the existing artifact.

## Storing and Fingerprinting Artifacts

1. Create a post-build action for archiving JAR files with the pattern `build/libs/*.jar`. Enable the fingerprinting option.
2. Execute the build. The build should list the artifact `gradle-initializr-1.0.0.jar`.
3. Have a look at the recorded fingerprints of this build.
4. Render the MD5 hash of the artifact and the usage of the artifact.
5. Install the [Copy Artifacts plugin](https://plugins.jenkins.io/copyartifact).
6. Create a downstream job named `consumer`.
7. Configure the downstream job to use the artifact produced by the upstream job.
8. Run the the build for the job `gradle-initializr`.
9. Have a look at the fingerprints of the downstream job.