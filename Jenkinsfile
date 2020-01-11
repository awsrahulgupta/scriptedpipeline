node('master') {
   stage('ContinuousDownloadloans') {
   git 'https://github.com/awsrahulgupta/scriptedpipeline.git'
}
stage('ContinuousBuildloans') {
    sh label: '', script: 'mvn package'
}
stage('ContinuousDeploymentloans') {
    sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.91.21:/var/lib/tomcat8/webapps/testenv.war'
}

}
