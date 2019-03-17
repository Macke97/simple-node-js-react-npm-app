pipeline {
    agent {
        docker {
            image 'node:10-alpine' 
            args '-p 3000:3000' 
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Installing') { 
            steps {
                sh 'yarn' 
            }
        }
        stage('Testing') {
            steps {
                sh './jenkins/scripts/test.sh'
                // sh './jenkins/scripts/kill.sh'
            }
        }
        // stage('Deliver') {
        //     steps {
        //         sh './jenkins/scripts/deliver.sh'
        //         // input message: 'Finished using the web site? (Click "Proceed" to continue)'
        //         sh './jenkins/scripts/kill.sh'
        //     }
        // }
    }
}