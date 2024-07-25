node('built-in')
{
    stage('ContDownload')
    {
        git 'https://github.com/intelliqittrainings/maven.git'
    }
    stage('ContBuild')
    {
        sh 'mvn package'
    }
    stage('ContDeploy')
    {
        deploy adapters: [tomcat9(credentialsId: 'ab501205-ec44-4672-9f5d-2aceaae01d9f', path: '', url: 'http://172.31.85.16:8080')], contextPath: 'testapp', war: '**/*.war'
    }
    stage('ContTesting')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
    }
}
