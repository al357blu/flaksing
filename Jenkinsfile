pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/al357blu/flasking.git', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t al357blu/flask_app .'
      }
    }

    stage('Docker login') {
      steps {
        sh 'docker login -u al357blu -p dckr_pat_iDuLAIG6KXekxbSW6A8N7Fo0SRg'
      }
    }

    stage('Docker push') {
      steps {
        sh 'docker push al357blu flask_app'
      }
    }

  }
}