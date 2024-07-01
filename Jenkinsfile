pipeline{
    agent any

    stages{
        stage('zip the file'){
            steps{
                sh 'zip ansible-${BUILD_ID}.zip * --exclude Jenkinsfile'
            }
        } 
        stage('upload artifacts to jfrog'){
            steps{
                sh 'curl -uadmin:AP23ECGyQnBamq6ENNe8okFtEr2 -T \
                ansible-${BUILD_ID}.zip \
                "http://35.153.57.235:8081/artifactory/ansible/ansible-${BUILD_ID}.zip"'
            }
        }   
    }
}