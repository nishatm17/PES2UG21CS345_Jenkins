pipeline{
  agent any 
  stages {
     stage('Clone repository'){
        steps{
        checkout([$class: 'GitSCM',
       branches:[[name:'*/main']],
        userRemoteConfigs :[[url:'https://github.com/nishatm17/PES2UG21CS345_Jenkins.git']]])
   }
   }
    stage('Build'){
      steps{
       sh 'g++ main/hello.cpp -o output'
      }
    }
    stage('Test'){
      steps {
        sh './output'
      }
    }
    stage('Deploy'){
      steps{
        echo 'deploy'
      }
    }
  }
  post{
    failure{
      error 'Pipeline failed'
    }
  }
}
