node{
    stage('git checkout'){
        git credentialsId: 'ancy-varghese-git', url: 'https://github.com/ancy-varghese-git/war-test.git'
    }
    stage('mvn build and test'){
        sh 'mvn clean package'
    }
    stage('Tomcat deploy')
    {
        deploy adapters: [tomcat8(credentialsId: 'tomcat', path: '', url: 'http://localhost:8888')], contextPath: 'annwar', war: '**/*.war'
    }
}