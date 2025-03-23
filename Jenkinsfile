pipeline {
    agent any
    }
environment {
    PATH = "/opt/apache-maven-3.9.9/bin:$PATH"
}
    stages {
        stage('Checkout'){
            steps { 
                git branch: 'main', url: 'https://github.com/gayathriarun001/tweet-trend.git'
           }
        }

        stage("build"){
            steps {
               sh 'mvn clean deploy -Dmaven.test.skip=true'
           }
        }
        stage("test"){
            steps{
                echo "------unit test started----"
                sh 'mvn surefire-report:report'
                echo "-------unit test completed----"
            }
        }
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

 



