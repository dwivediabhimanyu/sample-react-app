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
        steps {
            dir("sample-react-app/frontend") {
                echo "npm run build"
            } 
        }
      }

      stage("Deploy") {
        steps {
            dir("sample-react-app/frontend") {
                sh "rm -rfv /var/www/tutorial"
                sh "resync -a ./build/ /var/www/tutorial"
            } 
        }
      }
    }
}
