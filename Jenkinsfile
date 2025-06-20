pipeline {
    agent any 
    stages {
        stage('test') {
            steps { 
                script  {  
                     sh  '''
                          echo "Temp Change"
                          echo ""
                          curl wttr.in
                        '''
                    }
                }
            }
        }
    }
