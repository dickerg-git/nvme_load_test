pipeline {

    agent any

    stages {

        stage('Info') {
            steps {
                echo 'Info stage.'
                sh 'echo $HOME'
                sh 'ls -l $HOME/Public/*.bin'
                sh 'lsblk'
            }
        }

        stage('Commit') {
            steps {
                echo 'Firmware Commit stage.'
                sh 'nvme version'
            }
        }

        stage('Test') {
            steps {
                echo 'NVME Test stage.'
                sh 'fio $HOME/tools/FIO/NVME_4k_rand_qos.fio'
            }
        }

    } // end of stages list

} // end of the pipeline file
