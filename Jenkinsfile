stage 'Checking connectivity'

node {
    deleteDir()
    checkout scm

    ansiblePlaybook( 
        playbook: 'ping.yml',
        inventory: 'inventory.ini', 
        credentialsId: 'vagrant')
}
