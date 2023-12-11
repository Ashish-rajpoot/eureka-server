pipeline{
    agent any

    tools{
        jdk 'jdk17'
        maven 'maven_3.9.4'
    }

    triggers{
        pollSCM('* * * * *')
    }

    stages{
        stage("compile stage"){
            steps{
                sh 'mvn clean compile'
            }
        }
        stage("package stage"){
            steps{
                sh 'mvn clean package -DskipTests'
            }
        }
        stage("Building Docker Image"){
            steps{
                sh 'sudo -S docker image build -t eureka-server .'
            }
        }
        stage("Tag Docker Image"){
            steps{
                sh 'sudo docker tag eureka-server ashish142/eureka-server:1.0.0'
            }
        }
    }
}