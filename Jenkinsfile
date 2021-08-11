pipeline {
  agent any
  stages {
    stage('SonarQube analysis') {
      steps {
        withSonarQubeEnv('SonarQube') {
          script {
            def scannerHome = tool 'SonarScanner';
            def nodeHome = tool 'NodeJS';
            sh "${scannerHome}/bin/sonar-scanner -Dsonar.nodejs.executable=${nodeHome}/bin/node"
          }
        }
      }
    }
    stage('Quality Gate') {
      steps {
        timeout(time: 1, unit: 'HOURS') {
          waitForQualityGate abortPipeline: true
        }
      }
    }    
  }
}
