pipeline {
    agent any

    stages {
        // stage('Sonar Analysis') {
        //     steps {
        //         echo 'CODE QUALITY CHECK'
        //         sh 'cd webapp && sudo docker run  --rm -e SONAR_HOST_URL="http://34.222.106.155:9000" -e SONAR_LOGIN="sqp_31a2a065a5c706f2d31e4da19e61b346232ab619"  -v ".:/usr/src" sonarsource/sonar-scanner-cli -Dsonar.projectKey=lms'
        //         echo 'CODE QUALITY COMPLETED'
        //     }
        // }
        stage('run postgres container ') {
            steps {
                echo 'run postgres container'
                sh ' sudo docker container run -dt --name lms-db -e POSTGRES_PASSWORD=az123456 postgres'
                echo 'database container is running '
            }
        }
//         stage('Release LMS') {
//             steps {
//                 script {
//                     def packageJson = readJSON file: 'webapp/package.json'
//                     def packageJSONVersion = packageJson.version
//                     echo "${packageJSONVersion}"
//                     sh "zip webapp/lms-${packageJSONVersion}.zip -r webapp/dist"
//                     sh "curl -v -u admin:lms12345 --upload-file webapp/lms-${packageJSONVersion}.zip http://34.222.106.155:8081/repository/lms/"
//                 }
//             }
//         }

//         stage('Deploy LMS') {
//             steps {
//                 script {
//                     def packageJson = readJSON file: 'webapp/package.json'
//                     def packageJSONVersion = packageJson.version
//                     echo "${packageJSONVersion}"
//                     sh "curl -u admin:lms12345 -X GET \'http://34.222.106.155:8081/repository/lms/lms-${packageJSONVersion}.zip\' --output lms-'${packageJSONVersion}'.zip"
//                     sh 'sudo rm -rf /var/www/html/*'
//                     sh "sudo unzip -o lms-'${packageJSONVersion}'.zip"
//                     sh "sudo cp -r webapp/dist/* /var/www/html"       
//                 }
//             }
//         }

//     }
}
}

