pipeline{
	agent any
	stages {
		stage('Build') {
			tools{
				maven 'maven'
			}
				
			steps {
			sh 'mvn clean install package'
			archiveArtifacts artifacts :'**/*.war'
			}
        	}
        	stage('Build another job') {
            		steps {
                	build 'dockerbuild'
			}
            	}
    	}
}
