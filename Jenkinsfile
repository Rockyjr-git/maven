pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload_mains')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/maven.git'
            }
        }
        stage('ContinuousBuild_mains')
        {
            steps
            {
              sh label: '', script: 'mvn package'
            }
        }
        stage('ContinuousDeployment_mains')
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: '532262ae-46ac-4b78-b432-f0d14caae61c', path: '', url: 'http://172.31.1.50:8080')], contextPath: 'testapp', war: '**/*.war'
            }
            
        }
        stage('ContinuousTesting_mains')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/Declarative_Pipeline/testing.jar'
            }
        }
    }
