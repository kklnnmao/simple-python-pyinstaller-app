pipeline {
    agent any
    stages {
        stage('Build') { 
            agent {
                docker {
                    image 'python:2-alpine'
                    args '-v /var/run/docker.sock:/var/run/docker.sock'
                }
            }
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py'
            }
        }
    }
}