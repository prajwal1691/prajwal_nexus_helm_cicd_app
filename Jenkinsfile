pipeline{
  agent any
  stages{
    stage('sonar quality status'){
      agent{
        docker{
          image 'jenkins/jenkins:2.60.3-alpine'
        }
      }
      steps{
        script{
          withSonarQubeEnv(credentialsId: 'sonar-token') {
           sh 'mvn clean package sonar:sonar'
          }
        }
      }
    } 
  }
}
