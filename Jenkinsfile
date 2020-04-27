pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        withGradle() {
          sh './gradlew check'
        }

      }
    }

    stage('build') {
      steps {
        withGradle() {
          sh './gradlew build'
        }

      }
    }

  }
}