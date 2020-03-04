pipeline {
   // agent none
    agent any
    triggers {
        cron('* * * * *')
    }
    tools {
        maven 'LocalMaven323'
	jdk 'LocalJDK8'
    }
    stages {
	
	stage('Paquetizar mvn') {
	    agent {
                   label "win"
                }
             steps {
              	     git 'https://github.com/agangoiti/curso_integracion_continua.git'		
		     bat 'mvn clean test package'
                }
	     post { 
        	failure { 
           		echo 'Failure Cron'
        	}
    	     }
        }

    }
}
