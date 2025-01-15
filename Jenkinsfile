pipeline {
    agent any 
    stages {
        stage('test') {
            steps { 
                script  {  
                     sh  '''
                          curl wttr.in
                        '''
                    }
                }
            }
        }
    }
