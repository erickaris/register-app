pipeline {
  agent { label 'Jenkins-Agent' }
  tools {
    jdk 'Java17'
    maven 'Maven3'
  }
  stages{
      stage("Cleanup Workspace"){
              steps {
              cleanWs()
              }
      }
      stage("Checkout from SCM"){
              steps {
              git branch: 'feature', credentialsId: 'github', url: 'https://github.com/erickaris/register-app'
              }        
      } 
      stage("build application"){
              steps {
                sh "mvn clean package"
              }
      }
      stage("Test Application"){
            steps {
                sh "mvn test"
          }
      }
  }
}
