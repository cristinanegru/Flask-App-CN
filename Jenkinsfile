pipeline {

    agent any

    stages {

        stage('Clone') {

            steps {

                checkout scm

            }

        }

        stage('Build Docker Image') {

            steps {

                sh 'docker build -t currency-converter .'

            }

        }

        stage('Stop Old Container') {

            steps {

                sh 'docker stop currency-container || true'

                sh 'docker rm currency-container || true'

            }

        }

        stage('Run Container') {

            steps {

                sh 'docker run -d -p 80:5000 --name currency-container currency-converter'

            }

        }

    }

}
 
