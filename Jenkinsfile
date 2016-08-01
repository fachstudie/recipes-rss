approve{
      version = '0.0.1'
      console = 'http://fabric8.192.168.209.241.xip.io'
      environment = 'staging'
}

deployProject{
      stagedProject = 'recipes-rss'
      resourceLocation = 'target/classes/kubernetes.json'
      environment = 'staging'
}


node {
	def rc = getKubernetesJson {
		port = 8080
		label = 'node'
		icon = 'https://cdn.rawgit.com/fabric8io/fabric8/dc05040/website/src/images/logos/nodejs.svg'
		version = '0.0.1'
	}
	
	kubernetesApply(file: rc, environment: 'Development', registry: 'myexternalregistry.io:5000')
}