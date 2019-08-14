node {
    stage('SCM Checkout'){
        git credentialsId:'git-creds',url:'https://github.com/Divyavp/new.git'
    }
        
    
   
        
        stage('mvnpackage'){
            def mvnHome = tool name: 'newmav', type: 'maven'
            def mvnCMD = "${mvnHome}/bin/mvn"
            sh "${mvnCMD} clean package"
        }
        
    
    }
