# docker-dev-env
my own development environment.
##Docker images
###jenkines
Build command: docker build -t=jenkines-image .
run command: docker run --name=jenkins -v /f/docker-dev-env/jenkins/data:/data -p 8080:8080  jenkins-image
execute command: docker exec -it jenkins /bin/bash
execute command as root: docker exec -it -u root jenkins /bin/bash
admin user:mohammad
password: normal
email: shalabicloud@gmail.com
url: http://localhost:18080/
VM mapping:127.0.0.1:18080 - 8080

docker run --name=jenkins -v /f/docker-dev-env/jenkins/jenkins_home:/var/jenkins_home -p 8080:8080  jenkins