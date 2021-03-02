pipeline {
    agent {
        kubernetes {
            containerTemplate {
                name 'maven'
                image 'maven:alpine'
                ttyEnabled true
                command 'cat'
            }
            containerTemplate {
                name 'busybox'
                image 'busybox'
                ttyEnabled true
                command 'cat'
            }
        }
    }
    stages {
        stage('Run maven') {
            steps {
                container('maven') {
                    sh 'mvn -version'
                }
                container('busybox') {
                    sh '/bin/busybox'
                }
            }
        }
    }
}