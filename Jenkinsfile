pipeline {
    agent {
        node {
            label 'maven'
        }
    }
environment {
    PATH = "/opt/apache-maven-3.9.6/bin:$PATH"
}
    stages {
        stage('build') {
            steps {
                echo "-----Build started----"
                sh 'mvn clean deploy -Dmaven.test.skip=true'
                echo "-----Build Finished----"
            }
        }
        stage('test') {
            steps{
                echo "-----Test started----"
                sh 'mvn surefire-report:report'
                echo "-----Test Finished----"
            }
        }

        stage('SonarQube analysis') {
            environment {
            scannerHome = tool 'nihal-sonarqube-scanner'
            }
            steps{
            withSonarQubeEnv('nihal-sonarqube-server') { // If you have configured more than one global server connection, you can specify its name
            sh "${scannerHome}/bin/sonar-scanner"
            }
    }
  }

    }
}
