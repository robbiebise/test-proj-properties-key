node {
  stage('SonarQube analysis') {
    withSonarQubeEnv() {
      def scannerHome = tool 'SonarScanner 4.6.0';
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
