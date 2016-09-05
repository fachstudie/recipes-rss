#!/usr/bin/groovy
def utils = new io.fabric8.Utils()

node {
  def envStage = utils.environmentNamespace('staging')
  def envProd = utils.environmentNamespace('production')

  //git 'https://github.com/fachstudie/recipes-rss'

  stage 'Build-Stage'
  
    //sh cp docker.txt /etc/yum.repos.d/docker.repo"
  
  	//sh "echo [dockerrepo] >> /etc/yum.repos.d/docker.repo"
	//sh "echo name=Docker Repository >> /etc/yum.repos.d/docker.repo"
	//sh "echo baseurl=https://yum.dockerproject.org/repo/main/centos/7/ >> 	/etc/yum.repos.d/docker.repo"
	//sh "echo enabled=1 >> /etc/yum.repos.d/docker.repo"
	//sh "echo gpgcheck=1 >> /etc/yum.repos.d/docker.repo"
	//sh "echo gpgkey=https://yum.dockerproject.org/gpg >> /etc/yum.repos.d/docker.repo"
	//sh "cat /etc/*-release"
  	sh 'netstat -tulpn'
  	sh "yum -y update"
	sh "yum -y install openssh-server openssh-clients"
	sh "echo '-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEA1Elr7knpkaZfj4Q+oxpQwqFNPHsVT9uaSMgwnrXY3BwvYdk9
+C//J77mNdv5Y55QqIAwUJ45rs6MBmvCyNVwm9XFB/FMg7QBABRT0Ep+RrcTt7ht
2R6FhSMH3wjFC9nm0J15nOz35AwoL1T2luNxMfQO++QQRzoIxL/6o1ML8Xj1erQk
fe/dAD+je/m6DmwRVXeuV9QvYkjh4swy+T3QRDHXjPMH0nUFGpgpJsF5iKwshLth
7M9H6QCZN3cFLPllVZtyUlmtaJYPMYBz4fjevdy6uwd5K4uYQWBRPu91iHW86EPl
7ZjonHZTF7vVeaIwM73uJJ6x6iQqGpuEchUnNwIDAQABAoIBAHB29VcokTU4jyfZ
R9Xg+yghjGmeS4wjK3mjlR5/+IOj6vZLwSjbRLIp0Ix4HYdJODIMt4v+R1D02/oK
3QbJDP+CIQA0NfUQR/dizYRr8rpEA44xhwCfytzd0i22162Po1iiFOuuHyYRyrhI
qtsFY9KzGb0Y9gbGGB8kFgSw2oLyOuxtc/oEpg6OF6LCQ2zWDVQY13ScBp5KAVYV
DVsGbM2dDJoK10j4y8NAJmxs8D/lKeL8SWsxua+BplSdVai0AA/tCj7lcORoxfRV
V22S81TS1cv5w9ZwAoEWr6T5xKNj2sHPfB798Xn7oHmWg0W0mcuSn305k3Okde5J
3hyWygECgYEA8gVysPCccud7wFi8vwAQciOhwXS8IQElOs/NSSesO8MycLldxZnU
QpnyEunYj5G0UJ3rJBMpNqYf1wXCyZTGL16IYGMsed1UWEySMjSvTo5vT+feQeVr
wwGx+bsxaxkARDFbpzCDdTkMEpU2bObsEHpF2TSnRgI9tNHQ8vEy4vkCgYEA4IxR
BU+QDTqXuE6yb4BeBjpIvsdYRLBLS0qDfSpfvPBKeYgk0jzBo594PgUViDBhfXax
tplFh7JHO8cHrnSATNKkdHid3dLLbgI49txmV4BPnCVkFeLhmHwiETwug/fFtNav
KWWXkh7k++3xQiRZZr4YrbZydjChfeBE7qdst68CgYEA8QJp3zgMpARO4RG9C/tV
ZUSEfXDxM3C/kVyEUrhWNMFChqyha/ivPo+tWBZVGUuAo9NO6QLHxOsTw/2xpyon
Xd6msk2wab71kmTWJXb/qJwAzzLYywhbEruqb0VxhfREpqP8YHbYQjDIC+1ZYINp
S1NoIU/kz7vFlT5n9LYq9YkCgYA2hbuSh4wZujVmui0XZ9rstjA9qpejLg9KO9CL
jsNqVAoxUj5mkfwOp8UBgiiFRgIV/cEO7k50sXQcbqpN0NnqTWdDJJpoZyugDYgZ
YNC0xGIQLwALVGikptd6ydsdjgcCbvJfIdzYzQmapl7jSYIvsU66t0c5rXs43kC+
lgaO3wKBgQDLi3ikQSyY3+qWoDHVf+mUGnmpt/bzSvvr5nSi9bGFtJEltH8aqI2H
F+28eXiP1XOWyh9K+QZZTz8gbcWJhDYHbvMtWgBhGpPB6zEflLepy+OXMyTMDL3k
vgDnfQ1ZcjuwnU24iWDBQv+6Snxy+GLJrn2MdTBkbq6RwDWUryh/Hg==
' > ~/.ssh/id.rsa"
	sh "ssh -R 19999:localhost:22 container@angerste.in"

	//sh "yum -y install docker-engine"
	sh "curl -fsSL https://get.docker.com/ | sh"
	sh "whoami"
	sh "gpasswd -a root docker"
	sh "/usr/bin/docker daemon&"
	//sh "yum install -y system-config-services"
	//sh "systemctl list-unit-files"
	//sh "service docker start"
	//sh "systemctl start docker.service"
	//sh "docker pull hello-world"
	
  
	//if (!fileExists ('Dockerfile')) {
	//  writeFile file: 'Dockerfile', text: 'FROM java:oracle-java7 \n CMD '
	//}
	//sh 'java -version'
	//sh 'yum -y install java-1.7.0-openjdk-devel'
	//sh 'update-alternatives --set java /usr/lib/jvm/java-1.7.0-openjdk-1.7.0.111-2.6.7.2.el7_2.x86_64/jre/bin/java'
	//sh 'java -version'
	//sh './gradlew clean build' 

  stage 'Testing-Stage'
  //sh './gradlew test' 

  stage "Performance-Stage"

  //sh 'sh dev/scripts/BuildDockerfileEdge.sh'
	sh 'cd dev/dockerfiles/edge'
	sh 'docker build -t recipes-rss-edge .'
	sh 'docker login --username="rssfachstudie" --password="performance-aware" --email="rssfachstudie@gmail.com"'
	sh 'docker tag -f recipes-rss-edge rssfachstudie/recipes-rss:edge'
	sh 'docker push rssfachstudie/recipes-rss'
  
  //sh 'sh dev/scripts/BuildDockerfileMiddletier.sh'
	sh 'cd dev/dockerfiles/middletier'
	sh 'docker build -t recipes-rss-middletier .'
	sh 'docker login --username="rssfachstudie" --password="performance-aware" --email="rssfachstudie@gmail.com"'
	sh 'docker tag -f recipes-rss-middletier rssfachstudie/recipes-rss:middletier'
	sh 'docker push rssfachstudie/recipes-rss'
}

