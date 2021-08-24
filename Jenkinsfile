pipeline { 
  
   agent any

   stages {
   
     stage('Install Dependencies') { 
        steps { 
          echo "installing application" 
        }
     }
     
     stage('Test') { 
        steps { 
           sh 'echo "testing application..."'
        }
      }

         stage("Deploy nodejs application") { 
         steps { 
           sh 'echo "deploying application..."'
         }

     }
  
   	}

   }
