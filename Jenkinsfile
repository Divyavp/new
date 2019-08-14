pipeline {
    
   
        
        stage('mvnpackage'){
            def mvnHome = tool name: 'newmav', type: 'maven'
            def mvnCMD = "${mvnHome}/bin/mvn"
            sh "${mvnCMD} clean package"
        }
        
    
    }
