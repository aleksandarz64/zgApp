pipeline {
    agent any
    environment {
    APP_NAME = 'ZG-APP'
    BUILD_NUMBER = "${env.BUILD_NUMBER}"
    IMAGE_VERSION="v_${BUILD_NUMBER}"
    GIT_URL="https://github.com/aleksandarz64/zgWapp.git"
    }
    stages {
        stage('Initialize'){
            steps {
                echo 'STARTED'
                echo "BUILD_NUMBER: ${BUILD_NUMBER}"
            }
        }
        stage('Git checkout code'){
            steps {
                echo 'Git checkout started..'
                git "${GIT_URL}" 
            }
        }
        stage('Mvn clean') {
            steps {
              echo 'MAVEN clean..'
              sh 'cd /var/lib/jenkins/workspace/${APP_NAME}'
              sh 'pwd'
              sh 'mvn clean'

            }
        }
        stage('Mvn compile') {
            steps {
              sh 'MAVEN Compile..'
              sh 'cd /var/lib/jenkins/workspace/${APP_NAME}'
              sh 'mvn compile'
            }
        }
    }
}

