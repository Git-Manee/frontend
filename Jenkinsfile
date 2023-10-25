pipeline {
    agent { label 'workstation'}
    stages {

        stage('Code Quality'){
            steps{
                sh 'sonar-scanner -Dsonar.host.url=http://172.31.88.39:9000 -Dsonar.login=admin -Dsonar.password=admin123 -Dsonar.projectKey=frontend -Dsonar.qualitygate.wait=true'
            }
        }
        stage('Release'){
            steps{
                sh 'env'
                echo 'CI'
            }
        }
    }
}
///