stage 'Checking connectivity'

node {
    deleteDir()
    checkout scm

    ansiblePlaybook( 
        playbook: 'ping.yml',
        inventory: 'inventory.ini', 
        credentialsId: 'd9b0be15-1b29-4924-b91c-d25988375431')
}
