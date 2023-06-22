pipeline {
    agent any 
    tools {nodejs "node"}
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

      stage("InstallPackages") {
        steps {
            dir("sample-react-app/frontend") {
                sh "npm install"
            } 
        }
      }

      stage("Build") {
        steps {
            dir("sample-react-app/frontend") {
                sh "npm run build"
            } 
        }
      }

      stage("Deploy") {
        steps {
            dir("sample-react-app/frontend") {
                sh "rm -rfv /var/www/brightly"
                sh "rsync -a ./build/ /var/www/brightly"
            } 
        }
      }
    }
}
