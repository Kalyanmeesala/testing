node {
    stage('Delete existing workspace') {
        step([$class: 'WsCleanup'])
    }
    stage('Clone sources') {
        git url: 'https://github.com/Kalyanmeesala/testing.git', branch:'practice'
    }
    stage('Extract ZipFiles') {
        sh 'unzip volume-css.zip'
        sh 'pwd'
    }
     stage('Upload to S3 bucket') {
        step([
            $class: 'S3BucketPublisher',      
            entries: [[
                sourceFile: 'vallume/**/*',
                bucket: 'testingfrom-jenkins',
                selectedRegion: 'us-east-1',
                noUploadOnFailure: true,
                //managedArtifacts: true,
                //showDirectlyInBrowser: true,
                ]],
                profileName: 'TestUser',
                //dontWaitForConcurrentBuildCompletion: false,
                ])
    }
}
