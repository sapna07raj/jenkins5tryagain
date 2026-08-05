pipeline {
    agent any

    tools {
        jdk 'JDK21'
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code from GitHub'
            }
        }

        stage('Check Java Version') {
            steps {
                echo 'Checking Java installation'
                sh 'java -version'
                sh 'javac -version'
            }
        }

        stage('Compile') {
            steps {
                echo 'Compiling Java program'

                sh '''
                    javac -d . src/com/tyit/HelloJenkins.java
                '''
            }
        }

        stage('Run') {
            steps {
                echo 'Running Java program'

                sh '''
                    java com.tyit.HelloJenkins
                '''
            }
        }
    }

    post {

        success {
            echo 'Java build executed successfully in Jenkins'
        }

        failure {
            echo 'Java build failed'
        }

        always {
            echo 'Jenkins pipeline execution completed'
        }
    }
}
