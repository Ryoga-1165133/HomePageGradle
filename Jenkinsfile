pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        withGradle() {
          sh './gradlew check'
        }

        junit(testResults: 'build\\test-results\\test\\TEST-*.xml', healthScaleFactor: 1)
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