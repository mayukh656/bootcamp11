pipeline {
    agent any 
    stages {
       stage('code checkout'){
           steps {
              echo 'checking out the code'
              git 'https://github.com/mayukh656/war-test.git'
           }
       }
       stage('Compile') {
            steps {
                echo 'Compile the source code' 
            }
        }
       stage('build & test & package'){
           steps {
               sh 'mvn clean package'
           }
       } 
       stage('deploy'){
           steps {
              deploy adapters: [tomcat9(credentialsId: 'tomcat-creds', path: '', url: 'http://34.70.140.236:8888/')], contextPath: 'index23', war: '**/*.war'
           }
       }
    }
}
        
