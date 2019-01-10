pipeline {

    agent any

    stages {

        stage('Info') {
            steps {
                echo 'Info stage.'
                sh 'ls -l /home/rogerd/Public/*.bin'
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
                sh '/home/rogerd/tools/fio-3.12/fio --crctest=crc32'
            }
        }

    } // end of stages list

} // end of the pipeline file
