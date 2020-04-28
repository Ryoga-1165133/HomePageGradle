pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        withGradle() {
          sh './gradlew build'
        }

        junit(testResults: 'build\\test-results\\test\\TEST-*.xml', healthScaleFactor: 1)
        sh 'bash <(curl -s https://codecov.io/bash) -t 18c103fc-86c4-4e07-a735-97370d3fcdd7'
      }
    }

    stage('build') {
      steps {
        withGradle() {
          sh './gradlew bootWar'
        }

      }
    }

  }
}