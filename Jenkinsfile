pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        withGradle() {
          sh './gradlew check'
        }

        junit(testResults: 'build\\test-results\\test\\TEST-*.xml', healthScaleFactor: 1)
        archiveArtifacts './build/reports/jacoco/test/html/main.html'
      }
    }

    stage('build') {
      steps {
        withGradle() {
          sh '/var/jenkins_home/tools/hudson.plugins.gradle.GradleInstallation/gradle_6.3/bin/gradle bootWar'
        }

      }
    }

    stage('deploy') {
      steps {
        echo 'deployOK'
      }
    }

  }
}