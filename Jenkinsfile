pipeline {
      agent any
      stages {
            stage('Init') {
                  steps {
                        echo 'Hi, this is Hemanth'
                        
                  }
            }
            stage('Build') {
                  steps {
                        echo 'Building Sample Maven Project'
                  }
            }
            stage('Deploy') {
                  steps {
                        echo "Deploying in Staging Area"
                  }
            }
            stage('Deploy Production') {
                  steps {
                        echo "Deploying in Production Area"
                  }
            }
            
            stage('Publish') {
                   when {
                         branch 'master'
                        }
                   steps {
                          withDockerRegistry([ credentialsId: "dockerlogin", url: "" ]) {
                          sh 'docker push hemanthg781/terraform:latest'
                          sh 'docker push hemanthg781/cli:latest'
        }
      }
    }
      }
}
