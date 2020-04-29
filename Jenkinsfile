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
          sh '/var/jenkins_home/tools/hudson.plugins.gradle.GradleInstallation/gradle_6.3/bin/gradle bootWar'
        }

      }
    }

    stage('deploy') {
      steps {
        sh '''docker container run --name tomcat-test -p 80:8080 tomcat:latest
docker cp ./build/libs/HomePageGradle.war tomcat-test:/usr/local/tomcat/webapps'''
      }
    }

  }
}