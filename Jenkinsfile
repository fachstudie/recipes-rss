#!/usr/bin/groovy
def utils = new io.fabric8.Utils()

node {
  def envStage = utils.environmentNamespace('staging')
  def envProd = utils.environmentNamespace('production')

  git 'https://github.com/fachstudie/recipes-rss'

  stage 'Canary release'
  sh './gradlew clean build' 


  def newVersion = performCanaryRelease {}

  def rc = getKubernetesJson {
    port = 8080
    label = 'java'
    icon = 'http://www.iste.uni-stuttgart.de/fileadmin/user_upload/iste/zss/img/RSSBanner-WhiteBackground1.jpg'
    version = newVersion
    imageName = clusterImageName
  }

  stage 'Rolling upgrade Staging'
  kubernetesApply(file: rc, environment: envStage)

  stage 'Approve'
  approve{
    room = null
    version = canaryVersion
    console = fabric8Console
    environment = envStage
  }

  stage 'Rolling upgrade Production'
  kubernetesApply(file: rc, environment: envProd)

}

