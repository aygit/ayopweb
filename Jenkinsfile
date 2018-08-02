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
                    app = docker.build("ayopweb")
                }
            }


        stage('Push Docker Image') {


            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'ayodejiemiloju1') {
                        app.push("${env.BUILD_NUMBER}")
                        app.push("latest")
                    }
                }
            }
        }

}
