# Exercise 1

In this exercise, you will practice installing and configuring Jenkins on your machine. Feel free to experiment with a different Jenkins distribution than the proposed WAR file.

## Installing Jenkins

1. Download the [latest stable Jenkins WAR file](http://mirrors.jenkins.io/war-stable/latest/jenkins.war). To download from the command line, use `wget http://mirrors.jenkins.io/war-stable/latest/jenkins.war`.
2. Open a terminal and navigate to the directory containing the WAR file.
3. Run the command `java -jar jenkins.war` to start Jenkins on port 8080. Provide the `--httpPort` option if you experience a port conflict e.g. `java -jar jenkins.war --httpPort=9999`. For more information on starting and stopping Jenkins, see the [user guide](https://wiki.jenkins.io/display/JENKINS/Starting+and+Accessing+Jenkins). After a couple of seconds you should see the message "Jenkins is fully up and running" in the log output.
4. Open a browser of your choice and navigate to `localhost:<port>`. The default is `localhost:8080`.
5. In the screen named "Unlock Jenkins", enter the password from the console output. Press the "Continue" button.
6. In the screen named "Customize Jenkins", select the option "Install suggested plugins".
7. In the screen named "Create First Admin User", enter all fields with credentials for your Jenkins administrator. Press the "Save and Continue" button.
8. In the screen named "Instance Configuration", keep the default value. Press the "Save and Finish" button.
9. You should see the message "Jenkins is ready!". Press the "Start using Jenkins" button. You'll be redirected to the Jenkins dashboard.