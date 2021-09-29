pipeline {
  agent {dockerfile true}
  stages {
    
stage ('build'){
      steps{
        sh 'sudo docker build -t mstage:latest .'
      }
    }
    
  stage ('deploy'){
      steps{
        sh 'sudo docker run -d -p 9000:8080 mstage:latest'
      }
    }
    
     stage ('publish'){
      steps{
        sh 'sudo docker tag mstage:latest arjunaru25/mstagedh:1.0'
        sh 'sudo docker login -u arjunaru25 -p Dapplearu25'
        sh 'sudo docker push arjunaru25/mstagedh:1.0'
      }
    }

  }
}
