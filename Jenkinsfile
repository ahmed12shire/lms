pipeline {
    agent any

    stages {
    //     stage('Sonar Analysis') {
    //         steps {
    //             echo 'CODE QUALITY CHECK'
    //             sh 'cd webapp && sudo docker run  --rm -e SONAR_HOST_URL="http://35.183.78.18:9000" -e SONAR_TOKEN="sqp_9815fcb1959bedbe844b14defac4bc1fa3dd5fa5"  -v ".:/usr/src" sonarsource/sonar-scanner-cli -Dsonar.projectKey=lms'
    //             echo 'CODE QUALITY DONE'
    //         }
    //     }

    //     stage('Docker Login') {
    //         steps {
    //             script {
    //                 // Docker login
    //                 withCredentials([usernamePassword(credentialsId: 'dockerhub-credentials', passwordVariable: 'DOCKER_PASSWORD', usernameVariable: 'DOCKER_USERNAME')]) {
    //                     sh "docker login -u ${DOCKER_USERNAME} -p ${DOCKER_PASSWORD}"
    //                 }
    //             }
    //         }
    //     }

    //     stage('Run PostgreSQL Container') {
    //         steps {
    //             script {
    //                 echo 'Running PostgreSQL container'
    //                 def img = 'postgres'
    //                 docker.image(img).run("--name lms-db -e POSTGRES_PASSWORD=az123456 -d")
    //                 echo 'Database container is running'
    //             }
    //         }
    //     }

        stage('Build and Push Backend Docker Image') {
            steps {
                script {
                    echo 'Build and push backend Docker Image'
                    def packageJSON = readJSON file: 'api/package.json'
                    def packageJSONVersion = packageJSON.version
                    sh "cd api && docker build -t ahmed12shire/lms-backend-j:${packageJSONVersion} ."
                    sh "docker push ahmed12shire/lms-backend-j:${packageJSONVersion}"
                    echo 'Image build and push complete'
                }
            }
        }

        // stage('Run Backend Docker Container') {
        //     steps {
        //         script {
        //             echo 'Running backend container'
        //             sh "docker run -d --name lms-backend-j -p 8080:8080 ahmed12shire/lms-backend-j:${packageJSONVersion}"
        //             echo 'Backend container is running'
        //         }
        //     }
        // }

        // stage('Build and Push Frontend Docker Image') {
        //     steps {
        //         script {
        //             echo 'Build and push frontend Docker Image'
        //             def packageJSON = readJSON file: 'webapp/package.json'
        //             def packageJSONVersion = packageJSON.version
        //             sh "cd webapp && docker build -t ahmed12shire/lms-frontend-j:${packageJSONVersion} ."
        //             sh "docker push ahmed12shire/lms-frontend-j:${packageJSONVersion}"
        //             echo 'Image build and push complete'
        //         }
        //     }
        // }

        // stage('Run Frontend Docker Container') {
        //     steps {
        //         script {
        //             echo 'Running frontend container'
        //             sh "docker run -d --name lms-frontend-j -p 80:80 ahmed12shire/lms-frontend-j:${packageJSONVersion}"
        //             echo 'Frontend container is running'
        //         }
        //     }
        // }
    }
}
