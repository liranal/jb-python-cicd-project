pipeline {
  agent any

  stages {
    stage('Get repo') {
      steps {
        git branch: 'main', url: 'https://github.com/liranal/jb-python-cicd-project.git'
      }
    }

    stage('Build repo') {
      steps {
        script {
            try {
              docker.build("ec2-instance-describer:${env.BUILD_NUMBER}")
            } catch (err) {
                 echo "Error: ${err}"
                 currentBuild.result = 'FAILURE'
                 error "Build failed"
             }
        }
      }
    }
  }

  post {
        always {
            cleanWs()
        }
    }
}