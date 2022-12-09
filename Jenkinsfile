pipeline {
    
    agent{ label "MASTER" }    
    stages{
        stage ('Code Download From SCM'){
            steps{
                
                sh 'git clone https://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@github.com//hairavi10/sample-json.git'
                stash name: 'sample.json', includes: 'sample.json'
            }
        }
        
        stage('Read Json'){
            agent{ label "MASTER" }
            steps{
               sh '''                
                  
                     import json

                     with open('sample.json', 'r') as fcc_file:
                     fcc_data = json.load(fcc_file)
                     print(fcc_data)
                  '''
                        
                                                                   
                }                             
                                
            }
        }
        
    }
}
