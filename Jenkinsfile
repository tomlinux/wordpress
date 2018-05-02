pipeline {
    agent { dockerfile true }
    stages {
        stage('Test'){
            steps {
              sh echo "hello world"
            }
        }

    }
    stage('Push image') {
        /* Finally, we'll push the image with two tags:
         * First, the incremental build number from Jenkins
         * Second, the 'latest' tag.
         * Pushing multiple tags is cheap, as all the layers are reused. */
        docker.withRegistry('https://harbor.xuliang.xyz', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}
