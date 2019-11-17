# Solution

Create a new job.

![New Job](./images/new-job.png)

Configure the appropriate SCM.

![Job SCM](./images/job-scm.png)

Install the Go plugin.

![Go Plugin](./images/go-plugin.png)

Configure a Go runtime as global tool.

![Go Global Tool](./images/go-global-tool.png)

The `main.go` file could similar to the one below.

```go
package main

import "fmt"

func main() {
    fmt.Println("hello world")
}
```

The final `Jenkinsfile` looks similar to the solution below.

```groovy
pipeline {
    agent any
    tools {
        go 'go-1.12'
    }
    environment {
        GO111MODULE = 'on'
    }
    stages {
        stage('Build') {
            steps {
                sh 'go build'
            }
        }
    }
}
```

A build of the job installs the Go runtime and executes the build step.

![Declarative Pipeline](./images/declarative-pipeline.png)