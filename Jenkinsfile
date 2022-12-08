pipeline { 
    agent{ label "MASTER" }
    triggers{ pollSCM('* * * * *') }
    stages{
        stage ('Code Download From SCM'){
            steps{
                git 'https://github.com/hairavi10/sample-json.git'
                stash name: 'sample.json', includes: 'sample.json'
            }
        }
        
        stage('Read Json'){
            agent{ label "MASTER" }
            steps{
                dir('./'){
                      unstash name: 'sample.json'  
                                                                   
                }                             
                                
            }
        }
        
    }
}
