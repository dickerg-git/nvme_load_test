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
                sh '/home/rogerd/tools/nvme-cli/nvme version'
            }
        }

        stage('Test') {
            steps {
                echo 'NVME Test stage.'
                sh '/home/rogerd/tools/fio-3.12/fio /home/rogerd/tools/FIO/rand-rw.fio'
            }
        }

    } // end of stages list

} // end of the pipeline file
