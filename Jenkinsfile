pipeline {
  agent any
  stages {
    stage('Maven version') {
      steps {
        sh 'echo print maven version'
        sh 'mvn -version'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn clean package -DskipTests=true'
        archiveArtifacts 'target/hello-world-*.jar'
      }
    }

    stage('unit test') {
      steps {
        sh 'mvn test'
        junit(testResults: 'target/surefire-reports/TEST-*.xml', keepProperties: true, keepTestNames: true)
      }
    }

  }
  tools {
    maven 'M398'
  }
}