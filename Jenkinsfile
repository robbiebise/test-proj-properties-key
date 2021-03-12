pipeline {
  agent any
  stages {
    stage('SonarQube analysis') {
      steps {
        withSonarQubeEnv('SonarQube') {
          script {
            def scannerHome = tool 'SonarScanner';
            sh "${scannerHome}/bin/sonar-scanner"
          }
        }
      }
    }
  }
}
