pipeline {
    agent { label 'workstation'}
    stages {

        stage('Code Quality'){
            when {
                allof {
                    branch 'main'
                    expression { env.TAG_NAME != env.BRANCH_NAME }
                }
            }
            steps{
                sh 'sonar-scanner -Dsonar.host.url=http://172.31.88.39:9000 -Dsonar.login=admin -Dsonar.password=admin123 -Dsonar.projectKey=frontend -Dsonar.qualitygate.wait=true'
            }
        }
        stage('Release'){
            when {
                expression { env.TAG_NAME ==~ ".*" }
            }
            steps{
                sh 'env'
                echo 'CI'
            }
        }
    }
}
///