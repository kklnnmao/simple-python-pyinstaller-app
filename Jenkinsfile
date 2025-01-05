pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'python:2-alpine'
                }
            }
            steps {
                sh 'python2 -m py_compile sources/add2vals.py sources/calc.py'
            }
        }
    }
}