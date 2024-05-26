pipeline {
    agent any

    stages {
        // stage('Run PostgreSQL Container') {
        //     steps {
        //         script {
        //             echo 'Running PostgreSQL container'
        //             def img = 'postgres'
        //             docker.image(img).run("--name lms-db -e POSTGRES_PASSWORD=az123456")
        //             echo 'Database container is running'
        //         }
        //     }
        // }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build Docker image
                    sh "cd api && docker build -t ahmed12shire/lms-backend-j ."
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    // Run Docker container
                    sh "docker run -dt --name lms-backend-j -p 8080:8080 ahmed12shire/lms-backend-j"
                }
            }
        }
    }
}
