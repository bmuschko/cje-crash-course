# Solution

Change the list of Gradle tasks first.

![Gradle Tasks](./images/change-gradle-tasks.png)

Find the plugin and install it.

![Google Chat Plugin](./images/google-chat-plugin.png)

Add a new chat room.

![Chat Room](./images/create-room.png)

For the chat room, click the little cog icon and create a new webhook.

![Add Webhook](./images/add-webhook.png)

Enter an appropriate name for the webhook.

![Webhook Naming](./images/webhook-naming.png)

Copy the generate webhook URL to the clipboard.

![Webhook URL](./images/webhook-url.png)

In the Jenkins job, create a new Google Chat notification. Add the webhook URL and provide a name.

![Notification Configuration](./images/notification-config.png)

Run a build. It should fail and send a new message to the chat room.

![Chat Room Message](./images/chat-room-message.png)