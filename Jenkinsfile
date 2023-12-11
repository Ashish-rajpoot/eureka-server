pipeline{
    agent any
    tools{
        jdk 'jdk17'
        maven 'maven_3.9.4'
    }

    triggers{
        pollscm('* * * * *')
    }

    stages{
        stage("compile stage"){
            sh 'mvn clean compile'
        }
        stage("package stage"){
                    sh 'mvn clean package -DskipTests'
        }

    }

}