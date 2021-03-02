pipeline {
    agent {
        kubernetes {
            label: 'test',
            containers: [
                containerTemplate {
                    name 'maven'
                    image 'maven:alpine'
                    ttyEnabled true
                    command 'cat'
                },
                containerTemplate {
                    name 'busybox'
                    image 'busybox'
                    ttyEnabled true
                    command 'cat'
                },
                containerTemplate(
                    name: 'docker',
                    image: 'docker',
                    command: 'cat',
                    ttyEnabled: true
                ),
            ],
            volumes: [
                hostPathVolume(mountPath: '/var/run/docker.sock', hostPath: '/var/run/docker.sock'),
            ]
        }
    }
    stages {
        stage('Test') {
            steps {
                container('maven') {
                    sh 'mvn -version'
                }
                container('busybox') {
                    sh '/bin/busybox'
                }
                container('docker') {
                    sh 'docker version'
                }
            }
        }
    }
}