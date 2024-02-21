pipeline{
    agent any
    stages{
        stage('checkout the code of Banking '){
            steps{
                 git url: 'https://github.com/AshishNikam123/Banking-java-project/'
                 echo 'github url checkout'
            }
        }
        stage('Banking codecompile'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('Banking codetesting'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Banking codeqa'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('Banking codepackage'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Banking dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('Banking port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 myimg'
            }
        }   
    }
}
