pipeline {
    agent {
        kubernetes {
            yamlFile 'pod.yml'
            defaultContainer 'maven'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'id'
                sh 'mvn -B -DskipTests clean package'

            }
        }
        stage('Test') {
            steps {
                container('maven') {
                    sh 'mvn test'
                }
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}
