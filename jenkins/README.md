# Jenkins

## Upgrade existing instance

When a new version of Jenkins is released the following steps will upgrade seamlessly the existing instance.

1. Stop existing container

    `docker stop jenkins_1`
2. Pull the latest image

    `docker pull jenkins/jenkins:lts`
3. Start a container based on the latest image

    `docker run --name jenkins_2 --volumes-from jenkins_1 --restart unless-stopped -p 8080:8080 -p 50000:50000 -d jenkins/jenkins:lts`
4. Remove previous container

    `docker rm jenkins_1`
