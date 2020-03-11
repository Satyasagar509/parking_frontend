pipeline {
    agent any
        stages{
            stage('Git Checkout'){
                steps{
                    git 'https://github.com/Satyasagar509/parking_frontend.git'
                }
            }
            stage('Build') {
                steps{
                    sh 'npm install'
                    sh 'npm run build'
                    sh 'npm audit fix'
                }
            }
            stage('Deploy'){
                steps{
                    sh 'cp -R $WORKSPACE/build /var/workspace'
                    sh 'curl -u tomcat:admin123 http://3.12.161.159:8181/manager/reload?path=/build'
                }
            }
            }
        }
