pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        withGradle() {
          build(job: './gradlew check', wait: true)
        }

      }
    }

    stage('build') {
      steps {
        withGradle() {
          build(job: './gradlew bootWar', wait: true)
        }

      }
    }

    stage('deploy') {
      steps {
        echo 'DeployOK'
      }
    }

  }
}