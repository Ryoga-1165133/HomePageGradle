pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        git(url: 'https://github.com/krtnstk/HomePageGradle.git', branch: 'develop')
        withGradle() {
          build(job: 'check', wait: true)
          checkstyle()
          pmd()
          junit(allowEmptyResults: true, testResults: '*')
        }

      }
    }

    stage('build') {
      steps {
        withGradle() {
          build 'bootWar'
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