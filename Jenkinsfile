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
  
  stage('artifacctory storing'){
            steps{
              
                    script {
                        def server = Artifactory.server('jfrog-server')
               
                        def rtMaven = Artifactory.newMavenBuild()
                   
                        rtMaven.resolver server: server, releaseRepo: 'libs-release', snapshotRepo: 'libs-snapshot'
                        rtMaven.deployer server: server, releaseRepo: 'libs-release-local', snapshotRepo: 'libs-snapshot-local'
                        rtMaven.tool = 'maven3'
                        def buildInfo = rtMaven.run pom: 'pom.xml', goals: 'install'
                        server.publishBuildInfo buildInfo
                    }
            
            }
        }
}
}
