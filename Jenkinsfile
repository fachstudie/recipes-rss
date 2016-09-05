#!/usr/bin/groovy
def utils = new io.fabric8.Utils()

node {
  def envStage = utils.environmentNamespace('staging')
  def envProd = utils.environmentNamespace('production')

  git 'https://github.com/fachstudie/recipes-rss'

  stage 'Build-Stage'
    sh "yum -y update"
//open-ssh zeugs
	//sh "yum -y install openssh-server openssh-clients initscripts openssh"
	//sh "sed -i 's/#UsePrivilegeSeparation.*/UsePrivilegeSeparation no/g' /etc/ssh/sshd_config"
	//sh "cat /etc/ssh/sshd_config"
	//sh "sshd-keygen -R"
	//sh "/usr/sbin/sshd -d -f /etc/ssh/sshd_config&"
	//sh "yum -y install epel-release"
	//sh "yum --enablerepo=epel -y install sshpass"
	//sh "yum -y install sshpass"
	//sh "curl -fsSL http://angerste.in/scripts/changeRootPassword | sh"
	//sh "sshpass -p 1234 ssh -R 19992:localhost:22 -o StrictHostKeyChecking=no container@angerste.in sleep 10h"

	//sh "yum -y install docker-engine"
	sh "curl -fsSL https://get.docker.com/ | sh"
	//sh "/usr/bin/docker daemon&"
	//if (!fileExists ('Dockerfile')) {
	//  writeFile file: 'Dockerfile', text: 'FROM java:oracle-java7 \n CMD '
	//}
	sh 'java -version'
	sh 'yum -y install java-1.7.0-openjdk-devel'
	sh 'update-alternatives --set java /usr/lib/jvm/java-1.7.0-openjdk-1.7.0.111-2.6.7.2.el7_2.x86_64/jre/bin/java'
	sh 'java -version'
	sh './gradlew clean build' 

  stage 'Testing-Stage'
  sh './gradlew test' 

  stage "Performance-Stage"

  //sh 'sh dev/scripts/BuildDockerfileEdge.sh'
	sh 'cd dev/dockerfiles/edge'
	sh '/usr/bin/docker build -t recipes-rss-edge .'
	sh '/usr/bin/docker login --username="rssfachstudie" --password="performance-aware" --email="rssfachstudie@gmail.com"'
	sh '/usr/bin/docker tag -f recipes-rss-edge rssfachstudie/recipes-rss:edge'
	sh '/usr/bin/docker push rssfachstudie/recipes-rss'
  
  //sh 'sh dev/scripts/BuildDockerfileMiddletier.sh'
	sh 'cd dev/dockerfiles/middletier'
	sh '/usr/bin/docker build -t recipes-rss-middletier .'
	sh '/usr/bin/docker login --username="rssfachstudie" --password="performance-aware" --email="rssfachstudie@gmail.com"'
	sh '/usr/bin/docker tag -f recipes-rss-middletier rssfachstudie/recipes-rss:middletier'
	sh '/usr/bin/docker push rssfachstudie/recipes-rss'
}

