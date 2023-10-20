pipeline {
  agent any
  stages {
    stage("Set Up") {
      steps {
        script {
          sh """
          docker login -u ritesham -p excellent
          """
        }
      }
    }
    stage("Build docker Images") {
      steps {
        echo 'Build the staging image for more tests'
        script {
          sh """
          docker image build -t ritesham/vote:v1 vote/
          docker image build -t ritesham/worker:v1 worker/
          docker image build -t ritesham/result:v1 result/
          """
        }
      }
    }
    stage("Push to Docker Hub") {
      steps {
        script {
          sh """
          docker push ritesham/vote:v1
          docker push ritesham/result:v1
          docker push ritesham/worker:v1
          """
        }
      }
    }
    stage("Deploy to EKS Cluster") {
      steps {
        echo 'Deploy release to production'
        script {
          sh """
          echo "Hello World"
          """
        }
      }
    }
    stage("Clean Up") {
      steps {
        echo 'Clean up local docker images'
        script {
          sh """
          echo "Hello World"
          """
        }
      }
    }
  }
}
