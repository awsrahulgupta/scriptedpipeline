node('master') {
   stage('ContinuousDownloadloan') {
   git 'https://github.com/awsrahulgupta/scriptedpipeline.git'
}
stage('ContinuousBuildloans') {
    sh label: '', script: 'mvn package'
}

}
