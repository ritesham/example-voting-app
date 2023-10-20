pipeline {
  agent any
  stages {
    stage("Set Up") {
      steps {
        script {
          sh """
          sudo docker login -u ritesham -p excellent
          """
        }
      }
    }
    stage("Build docker Image") {
      steps {
        echo 'Build the staging image for more tests'
        script {
          sh """
          sudo docker image build -t ritesham/vote:v1 vote/
          sudo docker image build -t ritesham/worker:v1 worker/
          sudo docker image build -t ritesham/result:v1 result/
          """
        }
      }
    }
    stage("Push to Docker Hub") {
      steps {
        script {
          sh """
          sudo docker push ritesham/vote:v1
          sudo docker push ritesham/result:v1
          sudo docker push ritesham/worker:v1
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
