pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        sh './mvnw clean compile'
      }
    }

    stage('Static Analysis') {
      steps {
        sh '''./mvn sonar:sonar \\
  -Dsonar.projectKey=Simple-Java-Maven-App \\
  -Dsonar.host.url=http://172.31.19.201:9000 \\ /
  -Dsonar.login=sqp_91c32711e4e85a1d366ad514f5552e31c6dd62ed'''
      }
    }

  }
}