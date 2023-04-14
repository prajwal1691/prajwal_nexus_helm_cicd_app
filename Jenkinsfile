pipeline{
  agent any
  stages{
    stage('sonar quality status'){
      agent{
        docker{
          image 'jenkins/jenkins'
        }
      }
      steps{
        script{
          withSonarQubeEnv(credentialsId: 'sonar-token') {
           sh 'sudo mvn clean package sonar:sonar'
          }
        }
      }
    } 
  }
}
