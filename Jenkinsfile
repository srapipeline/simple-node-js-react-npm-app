Skip to content
 
Search or jump to…

Pull requests
Issues
Marketplace
Explore
 @srapipeline Sign out
0
0 1,307 srapipeline/simple-node-js-react-npm-app
forked from jenkins-docs/simple-node-js-react-npm-app
 Code  Pull requests 0  Projects 0  Wiki  Insights  Settings
simple-node-js-react-npm-app/jenkins/Jenkinsfile
b7dedaa  on 13 Oct 2017
@gilesgas gilesgas Add scripts to /jenkins/scripts directory + add Jenkinsfile example.
     
31 lines (30 sloc)  664 Bytes
pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
