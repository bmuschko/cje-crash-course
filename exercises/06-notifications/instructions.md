# Exercise 6

This exercise will demonstrate the use of a Google Chat room as way to send a notification upon a failed build. Given the locked down nature of Google Chat, this exercise will only be demonstrated by the instructor.

**This exercise will only be demonstrated on screen. You will be able to follow along if you have a [G Suite account](https://gsuite.google.com/products/chat/).**

## Notifying the Team Upon a Broken Build

1. Change the list of Gradle tasks to `doesnotexist` to emulate a failure. The build will fail as the task doesn't exist in the build script.
2. Install the [Google Chat Notification plugin](https://plugins.jenkins.io/google-chat-notification).
3. Create a new chat room in Google Chat named `jenkins-test` at [https://chat.google.com/](https://chat.google.com/).
4. For the chat room configure the webhook.
5. Configure the job to send a notification whenever the job fails. Use the webhook generated on Google Chat.
6. Execute the build. The build should fail and send a notification to the chat room.