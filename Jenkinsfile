node('master') {
   stage('ContinuousDownloadMasters') {
   git 'https://github.com/awsrahulgupta/scriptedpipeline.git'
}
stage('ContinuousBuildMaster') {
    sh label: '', script: 'mvn package'
}
stage('ContinuousDeploymentMaster') {
    sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.91.21:/var/lib/tomcat8/webapps/testenv.war'
}

stage('ContinuousTestingMaster') {
    git 'https://github.com/awsrahulgupta/functionaltesting.git'
    sh label: '', script: 'java -jar /home/ubuntu//.jenkins/workspace/ScriptedPipeline/testing.jar'
    }
stage('ContinuousDelieveryMaster') {
    input message: 'Waiting for Delivery Manager Approval', ok: 'Do you want to Deploy on Production Server.', submitter: 'Jyoti'
    sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.94.181:/var/lib/tomcat8/webapps/prodenv.war'
    }
}
