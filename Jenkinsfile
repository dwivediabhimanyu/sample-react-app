pipeline {
    agent any 
    stages {
      stage('Clean Up') {
        steps {
          echo 'Cleaning Workspace'
          deleteDir()
        }
      }
      stage("Checkout") {
        steps {
          sh "git clone https://github.com/dwivediabhimanyu/sample-react-app.git"
        }
      }

      stage("Build") {
        dir("sample-react-app/frontend") {
          echo "Build"
        }
      }

      stage("Test") {
        dir("sample-react-app/frontend") {
          echo "Test"
        }
      }
    }
}
