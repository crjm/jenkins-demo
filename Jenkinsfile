pipeline {
  agent any

  // assumes that the Dagger Cloud token
  // is in a Jenkins credential named DAGGER_CLOUD_TOKEN
  environment {
    DAGGER_CLOUD_TOKEN =  credentials('DAGGER_CLOUD_TOKEN')
  }

    // assumes a Go project
  // modify to use different function(s) as needed
  stages {
    stage("dagger") {
      steps {
        sh 'printenv'
        sh 'curl -v -u admin:f095ce071d12486d92762ec2a156a90c http://localhost:8080/userContent/dagger --output dagger'
        sh 'chmod +x dagger'
        sh './dagger version'
      }
    }
  }
}
