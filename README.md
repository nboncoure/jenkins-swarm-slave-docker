# Jenkins swarm slave

[`nboncoure/jenkins-swarm-slave`](https://registry.hub.docker.com/u/nboncoure/jenkins-swarm-slave/)

A [Jenkins swarm](https://wiki.jenkins-ci.org/display/JENKINS/Swarm+Plugin) slave.

For a container with ssh enabled see
[`nboncoure/jenkins-slave`](https://registry.hub.docker.com/u/nboncoure/jenkins-slave/)

## Running

To run a Docker container passing [any parameters](https://wiki.jenkins-ci.org/display/JENKINS/Swarm+Plugin#SwarmPlugin-AvailableOptions) to the slave

    docker run nboncoure/jenkins-swarm-slave -master http://jenkins:8080 -username jenkins -password jenkins -executors 1

Linking to the Jenkins master container there is no need to use `--master`

    docker run -d --name jenkins -p 8080:8080 nboncoure/jenkins-swarm
    docker run -d --link jenkins:jenkins nboncoure/jenkins-swarm-slave -username jenkins -password jenkins -executors 1


# Building

    docker build -t nboncoure/jenkins-swarm-slave .
