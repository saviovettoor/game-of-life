pipeline{
    agent any
    
    options{
        buildDiscarder(logRotator(numToKeepStr: '2', artifactNumToKeepStr: '1',  daysToKeepStr: '2'))
    }
    stages{
        stage('build'){
            steps{
                sh 'mvn clean install'
                sh 'mvn clean package'
                sh 'tar -cvzf gameoflife.tar.gz  target/easyb/*'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts:  'gameoflife.tar.gz', fingerprint: true
        }
        
    }

}
