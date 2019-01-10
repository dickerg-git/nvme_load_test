pipeline {

    agent any

    stages {

        stage('Info') {
            steps {
                echo 'Info stage.'
                sh 'pwd'
            }
        }

        stage('Commit') {
            steps {
                echo 'Firmware Commit stage.'
            }
        }

        stage('Test') {
            steps {
                echo 'NVME Test stage.'
            }
        }

    } // end of stages list

} // end of the pipeline file
