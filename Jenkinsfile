pipeline {
  agent any

  stages {
    stage('Checkout') {
        steps {
          // Get some code from a GitHub repository
          git branch: 'main', url: 'https://github.com/StuartC82/lbg-vat-calculator'
        }
    }
    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'sonarqube'
      }
        steps {
            withSonarQubeEnv('sonarqube') {        
              sh "${scannerHome}/bin/sonar-scanner"
            }   
        }
    }
  }
}
