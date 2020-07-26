pipeline {
    agent any
    
    stages {
        stage ('Build') {
            steps {
                sh 'rm -rf build'
                sh 'mkdir build'
                sh 'touch build/laptop.txt'
                sh 'echo "screen" > build/laptop.txt'
                sh 'echo "keyboard" >> build/laptop.txt'
                sh 'echo "motherboard" >> build/laptop.txt'
            }
        
        }
    
        stage('Test') {
            steps { 
                sh 'test -f build/laptop.txt'
                sh 'grep "screen" build/laptop.txt'
                sh 'grep "keyboard" build/laptop.txt'
                sh 'grep "motherboard" build/laptop.txt'
            }    
        }    
    
        stage('Publish') {
            steps {
                archiveArtifacts artifacts: 'build/'
            }
        }
    }
}
