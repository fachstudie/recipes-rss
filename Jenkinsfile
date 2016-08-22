#!/usr/bin/groovy
def utils = new io.fabric8.Utils()

node {
  def envStage = utils.environmentNamespace('staging')
  def envProd = utils.environmentNamespace('production')

  git 'https://github.com/fachstudie/recipes-rss'

  stage 'Build-Stage'
  if (!fileExists ('Dockerfile')) {
    writeFile file: 'Dockerfile', text: 'FROM java:oracle-java7 \n CMD '
  }
  sh 'java -version'
  sh 'yum -y install java-1.7.0-openjdk-devel'
  sh 'update-alternatives --set java /usr/lib/jvm/java-1.7.0-openjdk-1.7.0.111-2.6.7.2.el7_2.x86_64/jre/bin/java'
  sh 'java -version'
  sh './gradlew clean build' 

  stage 'Testing-Stage'
  sh './gradlew test' 

  stage "Performance-Stage"
  sh 'sh dev/scripts/BuildDockerfileEdge.sh'
  sh 'sh dev/scripts/BuildDockerfileMiddletier.sh'
  
}

