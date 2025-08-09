pipeline {
  agent { label 'Jenkins-agent' }
  tools {
    jdk 'Java17'
    maven 'maven3' // ensure this tool is configured in Jenkins Tool Configuration
  }
  stages {
    stage('Cleanup Workspace') {
      steps {
        cleanWs()
      }
    }
    stage('Checkout from SCM') {
      steps {
        git branch: 'main', credentialsId: 'github', url: 'https://github.com/Aishwaryakudtarkar2110/cicd'
      }
    }
    stage('Build Application') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage('Test Application') {
      steps {
        sh 'mvn test'
      }
    }
  }
}

  
