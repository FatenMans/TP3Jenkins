pipeline {
    agent any
  
    stages {
 stage('clean up') {
            steps {
                deleteDir()
            }
        }
       stage('clone repo') {
            steps {
                git branch: 'master', url: 'https://github.com/MedBouhdida1/Tp3Jenkins.git'
            }
        }
    
        stage('Build Spring') {
            
            steps {
                sh "mvn clean install"
                sh 'docker build -t backend .'
            }
        }
      
        stage('Run Docker compose') {
            steps {
                    sh 'docker-compose up -d'
                
            }
        }
    }
}
