node {
 
   notifyStarted()
 
   def workspace;
node
{
    
    stage('Checkout')
    {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '71749deb-4136-4d53-afa8-bf778005e554', url: 'https://github.com/sanyam90b/SimpleCustomerApp.git']]])
        workspace =pwd()
    }
    stage ('Static Code Analysis')
    {
        echo "Static Code Analysis"
    }
    stage('Build')
    {
        echo "Build the code"
    }
    stage('Unit Testing')
    {
        echo "Unit Testing"
    }
    stage ('Delivery')
    {
        echo "Deliver the code"
    }
}
   notifySuccessful()
 }
 
 def notifyStarted() { /* .. */ }
 
 def notifySuccessful()
 
   emailext (
       subject: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
       body: """<p>SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>
         <p>Check console output at "<a href="${env.BUILD_URL}">${env.JOB_NAME} [${env.BUILD_NUMBER}]</a>"</p>""",
       recipientProviders: [[$class: 'DevelopersRecipientProvider']]
     )
 }
