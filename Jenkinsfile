node {
    stage('Delete existing workspace') {
        step([$class: 'WsCleanup'])
    }
    stage('Clone sources') {
        git url: 'https://github.com/Kalyanmeesala/testing.git', branch:'testingnew'
    }
     stage('delete from S3 bucket') {
            sh 'rm test.txt'
    }
}
