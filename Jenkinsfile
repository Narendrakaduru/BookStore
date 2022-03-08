pipeline {
  agent any
  stages {
    stage('CheckOut SCM') {
      parallel {
        stage('CheckOut SCM') {
          steps {
            git(url: 'https://github.com/Narendrakaduru/BookStore.git', branch: 'master', credentialsId: 'GitCred')
          }
        }

        stage('Check POM') {
          steps {
            fileExists 'pom.xml'
          }
        }

      }
    }

    stage('Build ') {
      steps {
        sh 'mvn clean package'
      }
    }

  }
}