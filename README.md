# Jenkins Test
This is a simple repo that used the [Jenkins official docs installation guide](https://www.jenkins.io/doc/book/installing/docker)

## [alpine/socat container to forward traffic from Jenkins to Docker Desktop on Host Machine](https://stackoverflow.com/questions/47709208/how-to-find-docker-host-uri-to-be-used-in-jenkins-docker-plugin)
```
docker run -d --restart=always -p 127.0.0.1:2376:2375 --network jenkins -v /var/run/docker.sock:/var/run/docker.sock alpine/socat tcp-listen:2375,fork,reuseaddr unix-connect:/var/run/docker.sock
docker inspect <container_id> | grep IPAddress
```
In a Docker container running Jenkins, I was able to implement the Jenkinsfile to have a simple pipeline that runs the Python code under *myapp* folder
