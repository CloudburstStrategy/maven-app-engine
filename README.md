# maven-app-engine

A docker container for building, testing and deploying Jave/Maven/GoogleCloud/Terraform apps

    docker pull cloudburststrategy/maven-app-engine

This container is very useful for building GAE applications using the latest appengine-maven-plugin:

```XML
<dependency>
    <groupId>com.google.cloud.tools</groupId>
    <artifactId>appengine-maven-plugin</artifactId>
    <version>1.3.0</version>
</dependency>
```

---

Before you can use the plugin to upload your GAE app, you need to configure the authentication:

```Bash
echo $DEPLOY_KEY_FILE_PRODUCTION > .gitlab-ci.keyfile.json
gcloud auth activate-service-account --key-file .gitlab-ci.keyfile.json
```

---

This dockerfile is originally published to the docker repository: https://hub.docker.com/r/cloudburststratgey/maven-app-engine/


# Build

    docker build -t cloudburststrategy/maven-app-engine:latest .
    
# Push

    docker login (u: cloudburststrategy p: ***)
    docker push cloudburststrategy/maven-app-engine
