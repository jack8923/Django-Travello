pipeline {
    agent {
        docker {
            //image 'circleci/python:3.6'//'python:3-alpine'
            image 'rohitchandwani/pythonimage:latest'
        }
    }
    stages {
        stage ('Build') {
            steps {
                sh 'python3 -m venv venv'
                sh '. venv/bin/activate'
                sh 'pip3 install --user -r requirements.txt'
                //sh 'python manage.py test'
              
            }
        }
        stage ('Test') {
            steps {
                sh '. venv/bin/activate'
                sh 'python3 manage.py test'
            }
            
            //post {
            //    always {
            //        junit 'test-reports/results.xml'
            //    }
            //}
        }
    }
}
