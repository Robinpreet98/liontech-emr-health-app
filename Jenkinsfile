pipeline{
    agent slave1
    tools {
        maven "3.9.4"
    }
    stages{
        stage('clonefromsourcecode')
        {
            steps{
                sh "echo 'clone latest code from github'"
                sh "echo 'build developing for dev environment'"
                git 'https://github.com/Robinpreet98/liontech-emr-health-app.git'
            }
        }
        stage('Test+build+package'){
            steps{
                sh "echo 'running sonarqube code quality analysis'"
                sh "echo 'class20 devops engineers develop pipelines'"
                sh "echo 'testing must possoed inorder to package application'"
                sh "mvn install"
                sh "mvn validate"
                sh "mvn test"
                sh "mvn package"
            }
        }
        stage('codequality'){
            steps{
                sh "echo 'performing code quality analysis'"
                sh "mvn sonar:sonar"
            }
        }
        stage('uploadtonexus')
        {
            steps{
                sh "mvn deploy"
            }
        }
    }
    
}