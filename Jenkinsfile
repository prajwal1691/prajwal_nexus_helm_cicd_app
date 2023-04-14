pipeline{
  agent any
  stages{
    stage('sonar quality status'){
      agent{
        docker{
          image 'prajwal1691/jenkins-maven:jenkins-maven-v8'
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
