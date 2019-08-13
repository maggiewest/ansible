node('master') {
    def app

    stage("Clone repository") {
        checkout scm
        }



    stage("Run Ansible Playbook") {
        
            withCredentials([file(credentialsId: 'e7881201-b0c5-43cc-97cf-248ab66b464a', variable: 'mySecretKey')]){
            sh "pwd"
            sh "pwd"
            sh "ls"
            //sh "rm ohio.pem"
            sh "chmod -R 777 /var/lib/jenkins/workspace/maggie-ansible"
            sh "cp \$mySecretKey /var/lib/jenkins/workspace/maggie-ansible"
            sh "ls"
            sh "chmod 0400 ohio.pem"
            sh "python --version"
            sh "pip --version"
            sh "pip install --user boto"
            sh "pip install --user boto3"
            
            //sh "pip install boto"
            //sh "pip install boto3"
            //sh "pip install boto3 --ignore-installed ${six}"
            //sh "vi ~/.boto"
            sh "ansible-playbook create-ec2.yaml -i inventory.txt"
        }
            
          
        }
       
    

  
    stage("Wipe Out Jenkins Temp Workspace") {

      deleteDir()
       
    }

}
