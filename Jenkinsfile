pipeline {
    agent any
    stages {
        
        stage('mvnpackage'){
            def mvnHome = tool name: 'newmav', type: 'maven'
            def mvnCMD = "${mvnHome}/bin/mvn"
            sh "${mvnCMD} clean package"
        }
        
    
        stage('Build') {
            steps {
                 
                sh '${mvnCMD} -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                 
                sh '${mvnCMD} test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') { 
            steps {
                sh './jenkins/scripts/deliver.sh' 
            }
        }
    }
}
