node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'Sonarqube';  // Replace 'SonarScanner' with the actual tool name in Jenkins config
    withSonarQubeEnv('jenkins-sonar') {  // 'SonarQubeServer' is the name you configured in Jenkins
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
