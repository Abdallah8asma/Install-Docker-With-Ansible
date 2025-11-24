pipeline
{
    agent any
    stages{
        stage('Clone') {
          
            steps{
              git branch: 'main', credentialsId: 'Gitlab', url: 'git@gitlab.com:Abdallah8asma/installdocker.git'

        }
        }
        
        stage('Build') {

            steps{
                sh 'mvn clean install package'
            
        }}
        stage('install docker'){

          steps{
            ansiblePlaybook credentialsId: 'ansible', installation: 'ansible', inventory: 'hosts.yaml', playbook: 'install_docker.yaml', vaultTmpPath: ''

    }}

          

}

}
}

