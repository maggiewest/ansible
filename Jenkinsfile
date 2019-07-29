node('master') {
    def app

    stage("Clone repository") {
        checkout scm
        }



    stage("Run Ansible Playbook") {
        
            withCredentials([file(credentialsId: '0d089d5c-098a-4957-b768-a556fae36212', variable: 'mySecretKey')]){
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
