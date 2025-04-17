pipeline {
  agent any

  environment {
    IMAGE_NAME = "weathersphere"
    DOCKER_HUB_USER = "akgreninja"
  }

  stages {
    stage('Clone Repo') {
      steps {
        sh 'git config --global http.sslVerify false'
        git branch: 'main', url: 'https://github.com/akgithubgre/weathersphere.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh '''
          export DOCKER_BUILDKIT=0
          docker build -t $IMAGE_NAME .
        '''
      }
    }

    stage('Stop Previous Container') {
      steps {
        sh 'docker stop $IMAGE_NAME || true && docker rm $IMAGE_NAME || true'
      }
    }

    stage('Free Port 8080') {
      steps {
        powershell '''
          $tcpConnection = Get-NetTCPConnection -LocalPort 8080
          if ($tcpConnection) {
            $pid = $tcpConnection.OwningProcess
            Write-Host "Killing process on port 8080: $pid"
            Stop-Process -Id $pid -Force
          } else {
            Write-Host "Port 8080 is free"
          }
        '''
      }
    }

    stage('Run Docker Container') {
      steps {
        sh 'docker run -d -p 8080:80 --name $IMAGE_NAME $IMAGE_NAME'
      }
    }

    stage('Push to Docker Hub') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'USER', passwordVariable: 'PASS')]) {
          sh '''
            echo $PASS | docker login -u $USER --password-stdin
            docker tag $IMAGE_NAME $DOCKER_HUB_USER/$IMAGE_NAME:latest
            docker push $DOCKER_HUB_USER/$IMAGE_NAME:latest
          '''
        }
      }
    }
  }

  post {
    success {
      mail to: 'your_email@gmail.com',
           subject: "✅ Jenkins Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' Succeeded",
           body: "Good news!\n\nThe Jenkins build '${env.JOB_NAME} [${env.BUILD_NUMBER}]' completed successfully.\n\nCheck the build here: ${env.BUILD_URL}"
    }

    failure {
      mail to: 'your_email@gmail.com',
           subject: "❌ Jenkins Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' Failed",
           body: "Oops!\n\nThe Jenkins build '${env.JOB_NAME} [${env.BUILD_NUMBER}]' failed.\n\nCheck the build here: ${env.BUILD_URL}"
    }
  }
}
