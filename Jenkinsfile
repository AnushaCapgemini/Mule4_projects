pipeline {
    agent any
    tools { 
        maven 'mvn 3.5.4' 
        jdk 'jdk1.8' 
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }

        stage ('Git Checkout') {
            steps {
                git 'https://github.com/AnushaCapgemini/Mule4_projects.git'
            }
        }
		stage ('compile-package')
		{
		steps{
		sh 'mvn -f sample_mule4/pom.xml clean install test -Pchdev deploy -DmuleDeploy -e'
		}
		}
    }
}
