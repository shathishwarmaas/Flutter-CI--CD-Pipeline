
pipeline {
    agent none
    stages {
        stage ('Checkout') {
            steps {
                git branch: '$branch', credentialsId: '$password', url: '$link' //check out the git repo
            }
        }
        stage ('Flutter Doctor') {
            steps {
                sh "flutter doctor -v" //to check all required depedencies are installed
            }
        }
        stage ('Run Flutter Tests') {
            steps {
                sh "flutter tests" //to test the flutter app to build
            }
        }
        stage ('Flutter Build APK') {
            steps {
                sh "flutter build apk --split-per-abi" //build apk with split of android versions
            }
      
        stage('Cleanup') {
            steps {
                sh "flutter clean"
            }
        }
    }
}
