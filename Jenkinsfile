pipeline {
    agent {
        node {
            label 'maven'
        }
    }
environment {
    PATH = 
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