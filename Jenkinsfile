pipeline {
  agent {
    kubernetes {
      yamlFile 'pod.yml'
    }
  }
  
  stages {
    stage('Run Maven') {
        steps {
            container('maven') {
                sh 'mvn -version'
            }
        }
    }
  }
}