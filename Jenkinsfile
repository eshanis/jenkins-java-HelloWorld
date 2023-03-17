node {
    def app

    stage('Clone repository') {
      

        checkout scm
    }

    stage('Build image') {
  
       docker.build("eshnil/simplejavaapp")
    }

    stage('Test image') {
  
        docker.image('eshnil/simplejavaapp:latest').withRun() { c ->
            sh ' echo "tested" '
          
    }
        
        
    }
    
    stage('Run Docker container on Remote') {
            steps {
                sh 'docker -H tcp://107.21.59.88:4243 run   eshnil/simplejavaapp'
            }
        }
  
   
}
