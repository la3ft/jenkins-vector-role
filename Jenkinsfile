pipeline {
    agent {
        label 'centos7'
    }
    stages {
        stage('Git') {
            steps{
                git branch: 'main', credentialsId: '', url: 'git@github.com:la3ft/jenkins-vector-role.git'
            }
        }
        stage('Test'){
            steps{
                dir('roles/vector-role/') {
                sh 'molecule test -s default'
                }
                cleanWs()
            }
        }
    }
}