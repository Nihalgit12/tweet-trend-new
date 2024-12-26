pipeline {
    agent {
        node {
            label 'maven'
        }
    }
environment {
    PATH = "/opt/apache-maven-3.9.9/bin/"
}
    stages {
        stage ("Build") {
            steps {
                echo "------------Build Started-----------"
                sh mvn clean deploy
                echo "------------Build Ended-------------"
            }
        }
        }
    }