pipeline {
  agent {label 'slave1'}
  stages {
    
stage ('build'){
      steps{
        sh 'pwd'
        sh 'ls'
        sh 'docker build -t mstage:latest .'
      }
    }
    
     stage ('publish'){
      steps{
        sh 'docker tag mstage:latest arjunaru25/mstagedh:1.0'
        sh 'docker login -u arjunaru25 -p Dapplearu25'
        sh 'docker push arjunaru25/mstagedh:1.0'
      }
    }
    
  stage ('deploy'){
    agent {label 'slave2'}
      steps{
        sh 'docker login -u arjunaru25 -p Dapplearu25'
        sh 'docker pull arjunaru25/mstagedh:1.0'
        sh 'docker run -d -p 9000:8080 arjunaru25/mstagedh:1.0'
      }
    }
    


  }
}
