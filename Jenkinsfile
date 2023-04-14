pipeline{
  agent any
  stages{
    stage('sonar quality status'){
      agent{
        docker{
          image 'maven'
        }
      }
      steps{
        script{
          withSonarQubeEnv(credentialsId: 'sonar-token') {
            sh -X 'mvn clean package sonar:sonar'
          }
        }
      }
    } 
  }
}
