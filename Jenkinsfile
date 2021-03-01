node {
    stage('Stage 1') {
        echo 'Hello'
    }
    stage('Stage 2') {
        echo 'World'
        sh 'sleep 5'
    }
    stage('Stage 3') {
        echo 'Good to see you!'
    }
    stage('Flow Control') {}
        if (env.BRANCH_NAME == 'main') {
            echo 'I only execute on the main branch'
        } else {
            echo 'I execute elsewhere'
        }
    }
}