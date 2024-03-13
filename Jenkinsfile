pipeline {
    agent any
    stages {
        stage('Clone repository') {
        steps {
            checkout([$class: 'GitSCM',
            branches: [[name: '*/main']],
            userRemoteConfigs: [[url: 'https://github.com/suprkar/pes2ug21cs556_jenkins.git']]
            ])
        }
    }
    stage('Build') {
        steps {
            build 'PES2UG21CS534-1'
            sh 'g++ main.cpp -o output'
        }
    }
    stage('Test') {
        steps {
            sh './output'
        }
    }
}
post{
    failure{
        error 'Pipeline failed'
    }
}
}
