pipeline {
    agent none 
    stages {
        stage('Build') { 
            agent {
                any {
                    image 'python:3-alpine' 
                }
            }
            steps {
                sh 'python3 -m py_compile sources/add2vals.py sources/calc.py' 
            }
        }
    }
}