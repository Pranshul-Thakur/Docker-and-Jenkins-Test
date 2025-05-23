# Docker-and-Jenkins
Test Python files for Jenkins and Docker 
writing steps because i definitely wont forget them 

1) Install Docker on your local machine.
2) Run this command: `docker run -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk11`
3) Write down the password (written in notepad)
4) Go to `localhost on browser:8080` and you should be prompted for this password
5) create the pipeline
6) While the docker container is running, run cmd: `docker ps` to see what containers are running - copy the container ID for Jenkins : `0844bd58ea9a`
7) Run command: `docker exec -it -u 0 0844bd58ea9a /bin/bash` to open an interactive terminal within the Docker Container as root (user 0) 
8) Run command: `apt-get update` and `apt-get install python3` and `apt-get install python3-pip` to install Python3 and pip within the Docker container 
9) Run `pip install pytest` to install the pytest package that actually runs the unit/integ tests during your test stage within the pipeline
