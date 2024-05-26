pipeline {
    agent any

    stages {
         stage('Sonar Analysis') {
           steps {
               echo 'CODE QUALITY CHECK'
               sh 'cd webapp && sudo docker run  --rm -e SONAR_HOST_URL="http://35.183.78.18:9000" -e SONAR_LOGIN="sqp_7a4167a9fe7c997d0af3ff9a764ebeca6d1a8ced"  -v ".:/usr/src" sonarsource/sonar-scanner-cli -Dsonar.projectKey=lms'
               echo 'CODE QUALITY DONE'
           }
       }

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

    //     stage('Build frontend Docker Image') {
    //         steps {
    //             script {
    //                 echo 'Build backend Docker Image'
    //                 sh "cd api && docker build -t ahmed12shire/lms-backend-j ."
    //                 echo 'Image build complete'
    //             }
    //         }
    //     }
        
    //     stage('Push backend Docker Image') {
    //         steps {
    //             script {
    //                 // Push Docker image
    //                 sh "docker push ahmed12shire/lms-backend-j"
    //             }
    //         }
    //     }

    //     stage('Run backend Docker Container') {
    //         steps {
    //             script {
    //                 echo 'Running backend container'
    //                 sh "docker run -d --name lms-backend-j -p 8080:8080 ahmed12shire/lms-backend-j"
    //                 echo 'Backend container is running'
    //             }
    //         }
    //     }

//         stage('Build frontend Docker Image') {
//             steps {
//                 script {
//                     echo 'Build Docker Backend Image'
//                     sh "cd webapp && docker build -t ahmed12shire/lms-frontend-j ."
//                     echo 'Image build complete'
//                 }
//             }
//         }

//         stage('Push frontend Docker Image') {
//             steps {
//                 script {
//                     // Push Docker image
//                     sh "docker push ahmed12shire/lms-frontend-j"
//                 }
//             }
//         }

//         stage('Run frontend Docker Container') {
//             steps {
//                 script {
//                     echo 'Running frontend container'
//                     sh "docker run -d --name lms-frontend-j -p 80:80 ahmed12shire/lms-frontend-j"
//                     echo 'Backend container is running'
//                 }
//             }
//         }
    }
}
