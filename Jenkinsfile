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
        sh '''./mvnw sonar:sonar \\
  -Dsonar.projectKey=Simple-Java-Maven-App \\
  -Dsonar.host.url=http://3.109.0.59:9000 \\
  -Dsonar.login=sqp_91c32711e4e85a1d366ad514f5552e31c6dd62ed'''
      }
    }

    stage('Unit Test') {
      steps {
        sh './mvnw "-Dtest=**/petclinic/*/*.java" test'
      }
    }

  }
}