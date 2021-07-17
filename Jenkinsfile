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
}
