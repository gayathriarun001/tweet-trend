pipeline {
    agent none
    }
    stage('SonarQube analysis') {
    environment {
        scannerHome = tool "sonarqube-server"
    }
    // requires SonarQube Scanner 2.8+
    steps{
    withSonarQubeEnv('sonarqube-server') {
      sh "${scannerHome}/bin/sonar-scanner"
    }
    }
    }

 



