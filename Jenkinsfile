node{
    stage('code checkout'){
    echo 'checking out the code'
    git 'https://github.com/mayukh656/war-test.git'
    }
    
    stage('build & test & package'){
        sh 'mvn clean package'
    }
    
    stage('deploy'){
       deploy adapters: [tomcat9(credentialsId: 'tomcat-creds', path: '', url: 'http://34.70.140.236:8888/')], contextPath: 'index23', war: '**/*.war'
    }
}
