// node {
//   stage('SCM') {
//     checkout scm
//   }
//   stage('SonarQube Analysis') {
//     def scannerHome = tool 'Sonarqube';  // Replace 'SonarScanner' with the actual tool name in Jenkins config
//     withSonarQubeEnv('jenkins-sonar') {  // 'SonarQubeServer' is the name you configured in Jenkins
//       sh "${scannerHome}/bin/sonar-scanner"
//     }
//   }
// }
pipeline {
    agent any
    
    tools {
        // Use the name you set in Global Tool Configuration for SonarQube Scanner
        sonarScanner 'Sonarqube'
    }
    
    stages {
        stage('SonarQube Analysis') {
            steps {
                script {
                    withSonarQubeEnv('SonarQube') { // 'SonarQube' is the name of the server configured in Jenkins
                        // Run SonarQube analysis
                        sh 'sonar-scanner'
                    }
                }
            }
        }
    }
}
