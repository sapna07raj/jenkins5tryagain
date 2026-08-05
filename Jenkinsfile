pipeline {
    agent any

    tools {
        jdk 'JDK8'
    }

    stages {

        stage('Compile') {
            steps {
                echo 'Compiling Java program'
                bat 'javac src\\com\\tyit\\HelloJenkins.java'
            }
        }

        stage('Run') {
            steps {
                echo 'Running Java program'
                bat 'java -cp src com.tyit.HelloJenkins'
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
    }
}
