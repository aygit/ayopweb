pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh 'npm install'
                
            }
        }


        stage('Build Docker Image') {
            
            steps {
                script {
                    app = docker.build("ayodejiemiloju1")
                }
            }
          }

        stage('Push Docker Image') {


            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'a1de5c2a-dffe-4446-8c99-23bb67b5a5b7') {
                        app.push("${env.BUILD_NUMBER}")
                        app.push("latest")
                    }
                }
            }
        }
     }
   
}
