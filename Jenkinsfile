pipeline {
    agent any

    stages {
        stage('Docker Login') {
            steps {
                script {
                    // Docker login
                    withCredentials([usernamePassword(credentialsId: 'dockerhub-credentials', passwordVariable: 'DOCKER_PASSWORD', usernameVariable: 'DOCKER_USERNAME')]) {
                        sh "docker login -u ${DOCKER_USERNAME} -p ${DOCKER_PASSWORD}"
                    }
                }
            }
        }
        
        // stage('Run PostgreSQL Container') {
        //     steps {
        //         script {
        //             echo 'Running PostgreSQL container'
        //             def img = 'postgres'
        //             docker.image(img).run("--name lms-db -e POSTGRES_PASSWORD=az123456 -d")
        //             echo 'Database container is running'
        //         }
        //     }
        // }

        // stage('Build Docker Image') {
        //     steps {
        //         script {
        //             echo 'Build Docker Backend Image'
        //             sh "cd api && docker build -t ahmed12shire/lms-backend-j ."
        //             echo 'Image build complete'
        //         }
        //     }
        // }
        
        stage('Push Docker Image') {
            steps {
                script {
                    // Push Docker image
                    sh "docker push ahmed12shire/lms-backend-j"
                }
            }
        }

        // stage('Run Docker Container') {
        //     steps {
        //         script {
        //             echo 'Running backend container'
        //             sh "docker run -d --name lms-backend-j -p 8080:8080 ahmed12shire/lms-backend-j"
        //             echo 'Backend container is running'
        //         }
        //     }
        // }
    }
}
