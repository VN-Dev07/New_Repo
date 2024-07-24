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
        deploy adapters: [tomcat9(credentialsId: '81ca1393-2c6e-4561-a096-741ade21d7dc', path: '', url: 'http://172.31.48.151:8080')], contextPath: 'testapp', war: '**/*.war'
    }
    stage('ContTesting')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
    }
}
