node('master') 
{
    stage('ConDownload')
    {
        git 'https://github.com/intelliqittrainings/maven.git'
    }
    stage('ConBuild')
    {
        sh label: '', script: 'mvn package'  
    }
    stage('Condeploy')
    {
        sh label: '', script: 'scp /var/lib/jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.1.172:/var/lib/tomcat8/webapps/testapp.war'
    }
    stage('ConTesting')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        
        sh label: '', script: 'java -jar /var/lib/jenkins/workspace/ScriptedPipeline/testing.jar'
    }
}
