pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M398"
    }

    stages {
        stage('Maven version'){
            steps {
                sh 'echo print maven version'
                sh 'mvn -version'
            }
        }
        stage('Build'){
            steps{
                //getting code from git repo
                //git branch: 'main', url: 'https://github.com/Asimshaikh1908/jenkins-hello-world.git'
                
                //run mvn pkg cmd
                sh "mvn clean package -DskipTests=true"
                
            }
        }
        stage('unit test'){
            steps{
                sh "mvn test"
            }
        }
     
    }
}
