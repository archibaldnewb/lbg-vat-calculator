pipeline {
  agent any

  stages {
    stage('Checkout') {
        steps {
          git branch: 'main', url: 'https://github.com/archibaldnewb/lbg-vat-calculator.git'
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
