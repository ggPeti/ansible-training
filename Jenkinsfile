stage 'Checking connectivity'

node {
    deleteDir()
    checkout scm

    ansiblePlaybook( 
        playbook: 'ping.yml',
        inventory: 'inventory.ini', 
        credentialsId: 'vagrant')
}

stage "Check syntax"

node {

    wrap([$class: 'AnsiColorBuildWrapper', colorMapName: "xterm"]) {
        ansiblePlaybook(
            playbook: 'webserver.yml',
            inventory: 'inventory.ini',
            credentialsId: 'vagrant',
            extras: '--syntax-check',
            colorized: true
            )
    }
}

stage "Check dry-run"

node {
    wrap([$class: 'AnsiColorBuildWrapper', colorMapName: "xterm"]) {
        ansiblePlaybook(
            playbook: 'webserver.yml',
            inventory: 'inventory.ini',
            credentialsId: 'vagrant',
            extras: '--check --diff',
            colorized: true
            )
    }
}
