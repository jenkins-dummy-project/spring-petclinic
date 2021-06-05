pipeline{
    agent {
        label 'MASTER'
    }

    stages{

        stage('Pull Repo'){
            steps {
                git 'https://github.com/jenkins-dummy-project/spring-petclinic.git'
                
            }
        }

        stage('Build'){
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Publish'){
            steps{
                junit allowEmptyResults: true, testResults: 'target/surefire-reports/*.xml'
            }
            
        }
    }
