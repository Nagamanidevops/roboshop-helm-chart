pipeline {

    agent any
        
        parameters {
        
         string(name: 'COMPONENT', defaultValue: '', description: 'Component') 
         string(name: 'APPVERSION', defaultValue: '', description: 'App Version') 
        
        }
        
        stages {
        
            stage('get valeus file'){
            
            steps {
            
                dir('APP') {
                git branch: 'main', url: 'https://github.com/Nagamanidevops/${COMPONENT}.git'
                
            
            }
            
            }
            
            }
            stage('helm deploy'){
            
                steps {
                    sh ' helm upgrade -i cart . -f APP/values.yml --set -string image.tag=${APP_VERSION}'
                }
            }
        
        }
}