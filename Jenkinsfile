node() {
    stage('Checkout') {
        checkout scm
        commit_hash = sh(script: 'git rev-parse HEAD', returnStdout: true).trim()
        echo "commit_hash: "+ commit_hash
    }
    stage('deploy'){
        sh 'cd ansible && sudo ansible-playbook PushMultiArtifacts_new.yml --extra-vars=${commit_hash}'
    }
}
