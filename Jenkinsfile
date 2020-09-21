pipeline
{
agent any
stages
{
stage('first step')
{
steps{
bat"mvn clean install"
}
  
}
  stage('deploying')
  {
    steps{
      bat" [tomcat8(credentialsId: '5866d9c5-7497-4a2f-9477-39037e355cb6', path: '', url: 'http://localhost:8083/')], contextPath: 'C:/Program Files/Apache Software Foundation/Tomcat 8.5_Tomcat1/webapps', war: 'C:/Users/I11200047/.jenkins/workspace/multibranch-webapp_master/target/*.war'"
}
}
