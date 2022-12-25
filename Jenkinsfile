node {

	def mavenHome = tool name : 'Maven3.8.6'    //defines variable and assigns Maven tool to it

					
	stage ('1cloneCode'){  //called stage 1
        sh "rm -rf ./*"
        git credentialsId: 'TMRDevOps', url: 'https://github.com/TMRDevOps/mwaTMR2.git'

	}
	stage ('2Test&Build'){
		sh "${mavenHome}/bin/mvn clean package"  //runs maven from tool kit -> Maven not installed on server
		
	}
	stage ('3codeQuality'){
		sh "${mavenHome}/bin/mvn clean sonar:sonar"  //runs maven from tool kit -> Maven not installed on server
		
    }
}