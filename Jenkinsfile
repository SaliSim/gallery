pipeline { 
  agent any
  tools { 
    nodejs "NodeJs123"
  }
  stages { 
    stage('clone repository') {
      steps { 
        git 'https://github.com/SaliSim/gallery.git'
      }
    }
    stage('install dependancies') {
      steps { 
        sh 'npm install'
      }
    }
    stage('slack intergration'){
        steps{
            slackSend channel: '#ip1-project', message: "Slack intergration succesful of ${env.JOB_NAME} build number  ${env.BUILD_NUMBER}", teamDomain: 'saliip1', tokenCredentialId: 'slack'
        }
    }
    stage('Tests') {
      post{ 
        failure{
            mail bcc: '', body: 'This is a test email', cc: 'sali.simiyu@student.moringaschool.com', from: '', replyTo: '', subject: 'Failure', to: 'salisimiyu319@gmail.com'
      }
    }
    steps{ echo 'hello world'
    }
  }
 }
}
