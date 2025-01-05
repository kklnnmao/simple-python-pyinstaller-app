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
        stage('Test') { 
            agent {
                any {
                    image 'qnib/pytest' 
                }
            }
            steps {
                sh 'py.test --verbose --junit-xml test-reports/results.xml sources/test_calc.py' 
            }
            post {
                always {
                    junit 'test-reports/results.xml' 
                }
            }
        }
    }
}