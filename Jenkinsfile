pipeline {
    agent any 
    stages {
        stage('test') {
            steps { 
                script  {  
                     sh  '''
                          curl https://raw.githubusercontent.com/redhat-appstudio/tssc-sample-sbom-scans/refs/heads/main/live-demo
                        '''
                    }
                }
            }
        }
    }
