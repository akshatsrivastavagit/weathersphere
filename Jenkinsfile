pipeline {
  agent any

  environment {
    IMAGE_NAME = "weathersphere"
    DOCKER_HUB_USER = "akgreninja"
  }

  stages {
    stage('Clone Repo') {
      steps {
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
      mail to: 'youremail@example.com',
           subject: "✅ Build Successful - WeatherSphere",
           body: "The Docker container was built and deployed successfully."
    }
    failure {
      mail to: 'youremail@example.com',
           subject: "❌ Build Failed - WeatherSphere",
           body: "Something went wrong. Please check the Jenkins logs."
    }
  }
}
