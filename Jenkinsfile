pipeline {
    agent { label 'JDK-11'}
    triggers {
       pollSCM('*/15 * * * *')
    }
    stages {
        stage ('source code  from git remote repository') {
            steps {
                git url: 'https://github.com/ksumankumar/StudentCoursesRestAPI.git',
                 branch: 'master'
            }
        }
        stage('docker info') {
            steps {
                sh 'docker info'
            }
        }
        stage("image list") {
            steps { 
                sh 'docker image ls'   
            }
        }
        stage("image pull") {
            steps {
                sh 'docker image pull 8520005318/studentinfoapi'
            }
        }
        stage("container run") {
            steps {
                sh 'docker container run -d --name studapi -P 8520005318/studentinfoapi'
            }
        }
    }
}    
         
           
         
        
    
