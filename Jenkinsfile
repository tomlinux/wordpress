pipeline {
    agent { dockerfile true }
    stages {
        stage('Test'){
            steps {
              echo "hello world"
            }
        }

	    stage('Push image') {
        	docker.withRegistry('https://harbor.xuliang.xyz', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        	}
    	}
    }      
    
}
