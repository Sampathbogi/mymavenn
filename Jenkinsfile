node('built-in') 
{
     stage('ContinuousDownload') 
     {
        git 'https://github.com/intelliqittrainings/maven.git'
     }
     stage('ContinuousBuild') 
     {
        sh 'mvn package'
     }
     stage('ContinuousDeployment') 
     {
          deploy adapters: [tomcat9(credentialsId: '9a5127c8-6cac-4ccb-9a19-3a2637f8017f', path: '', url: 'http://172.31.10.243:8080')], contextPath: 'test', war: '**/*.war'
     }
      stage('ContinuousTesting') 
     {
         git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
         sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline2/testing.jar'
     }
      stage('ContinuousDelivery') 
     {
        
     deploy adapters: [tomcat9(credentialsId: '19718dfc-f0ba-4f4f-84c4-cdcad2b7aa28', path: '', url: 'http://172.31.0.248:8080')], contextPath: 'prodapp', war: '**/*.war'
     }
     
     
     
     
     
     
     
     
     
     
     
     
}
