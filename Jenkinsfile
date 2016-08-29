#!/usr/bin/groovy
def utils = new io.fabric8.Utils()

node {
  def envStage = utils.environmentNamespace('staging')
  def envProd = utils.environmentNamespace('production')

  //git 'https://github.com/fachstudie/recipes-rss'

  stage 'Build-Stage'
	
    //sh cp docker.txt /etc/yum.repos.d/docker.repo"
  
  	sh "echo [dockerrepo] >> /etc/yum.repos.d/docker.repo"
	sh "echo name=Docker Repository >> /etc/yum.repos.d/docker.repo"
	sh "echo baseurl=https://yum.dockerproject.org/repo/main/centos/7/ >> 	/etc/yum.repos.d/docker.repo"
	sh "echo enabled=1 >> /etc/yum.repos.d/docker.repo"
	sh "echo gpgcheck=1 >> /etc/yum.repos.d/docker.repo"
	sh "echo gpgkey=https://yum.dockerproject.org/gpg >> /etc/yum.repos.d/docker.repo"
	sh "cat /etc/*-release"
  
	sh "yum -y install docker-engine"
	//sh "yum install -y system-config-services"
	//sh "systemctl list-unit-files"
	//sh "service docker start"
	//sh "systemctl start docker.service"
	//sh "docker version"
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
  sh 'sh dev/scripts/BuildDockerfileEdge.sh'
  sh 'sh dev/scripts/BuildDockerfileMiddletier.sh'
  
}

