pipeline {
    agent {
        node {
            label "maven"
        }
    }

    stages {
        stage("clone-code") {
            steps {
                git branch: 'main', url: "https://github.com/gayathriarun001/tweet-trend.git"
            }
        }
    }

environment {
    PATH = "/opt/maven/bin:$PATH"
}
    stages {
        stage("build"){
            steps {
                sh 'mvn clen deploy'
            }
       }
   }
}