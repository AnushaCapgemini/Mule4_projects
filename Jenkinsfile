pipeline {
    agent any
    tools { 
        maven 'local_maven' 
        jdk 'local_java' 
    }
    stages {
        stage ('Initialize') {
            steps {
                bat '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }

        stage ('Git Checkout') {
            steps {
                git 'https://github.com/AnushaCapgemini/Mule4_projects/tree/master/sample_mule4'
            }
        }
		stage ('compile-package')
		{
		steps{
		bat 'mvn package'
		}
		}
    }
}
