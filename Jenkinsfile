pipeline {
   // agent none
    agent any
    triggers {
        cron('* * * * *')
    }
    tools {
        maven 'LocalMaven323' 
    }
    stages {
	
	stage('Paquetizar mvn') {
	    agent {
                   label "win"
                }
             steps {
              		bat 'mvn clean test package'
                }
        }
	post { 
        	failure { 
           		echo 'Failure Cron'
        	}
    	}
    }
}
