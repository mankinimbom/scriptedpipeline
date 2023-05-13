node('slave') 
{
         stage('ContinuesDownload') 
         {
             git 'https://github.com/mankinimbom/maven.git'
         }
         stage('ContinuesBuild') 
         {
            sh 'mvn clean install package'
         }
         stage('ContinueTesting') 
         {
            git 'https://github.com/mankinimbom/testingproject.git'
            sh 'java -jar /home/mint/workspace/scriptedtedpipline1/testing.jar'
            
         }
         stage('ContinuesDeployment') 
         {
            deploy adapters: [tomcat9(credentialsId: 'e49623cc-8130-408e-a881-17d029847267', path: '', url: 'http://10.0.0.76:8080')], contextPath: 'tina', war: '**/*.war'
         }
