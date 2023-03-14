node {
    def app

    stage('Clone repository') {
      

        checkout scm
    }

    stage('Build image') {
  
       app = docker.build("eshnil/simplejavaapp")
    }

    stage('Test image') {
  
        docker.image('eshnil/simplejavaapp:latest').withRun() { c ->
            sh ' echo "tested" '
            sh ' java HelloWorld'
    }
        
    }
  
   
}
