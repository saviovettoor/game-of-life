pipeline{
    agent any
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
            archive 'target/easyb/gameoflife.tar.gz'
        }
        
    }

}
