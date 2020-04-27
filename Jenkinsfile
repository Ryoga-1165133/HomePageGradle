pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        withGradle() {
          sh '/var/jenkins_home/tools/hudson.plugins.gradle.GradleInstallation/gradle_6.3/bin/gradle check'
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

    stage('deploy') {
      steps {
        echo 'DeployOK'
      }
    }

  }
}