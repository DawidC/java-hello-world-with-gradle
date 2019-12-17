pipeline {
    agent any 

    stages {
        stage('Git pull'){
            agent any
            steps {
                git 'https://github.com/DawidC/java-hello-world-with-gradle'
        
            }
        }
        
        stage('Build Assets jar') {
            agent any 
            steps {
                sh './gradlew jar'
            }
        }
        stage('run'){
            agent any
            steps{
                sh 'java -jar build/libs/HelloWorld.jar '
            }
        }
        stage('Test') {
            agent any
            steps {
                sh 'gradle test'
            }
        }
    }
}