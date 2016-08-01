node {
   // Mark the code checkout 'stage'....
   stage 'checkout'

   // Get some code from a GitHub repository
   git url: 'https://github.com/fachstudie/recipes-rss'
   sh 'git clean -fdx; sleep 40;'

   // Get the maven tool.
   // ** NOTE: This 'mvn' maven tool must be configured
   // **       in the global configuration.
   def mvnHome = tool 'mvn'
   
   
}

approve {
	console = fabric8Console
	environment = "${env.JOB_NAME}-staging"
}