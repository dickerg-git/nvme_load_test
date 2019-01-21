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
                sh 'sudo /usr/local/sbin/nvme version'
                sh 'sudo /usr/local/sbin/nvme list'
                sh 'sudo /usr/local/sbin/nvme fw-download --fw=/home/roger/Public/nvme_test_fw_to_load.bin /dev/nvme0n1'
                sh 'sudo /usr/local/sbin/nvme fw-commit --slot=2 --action=3 /dev/nvme0n1'
                sh 'sleep 3'
            }
        }

        stage('Test') {
            steps {
                echo 'NVME Test stage.'
                sh 'sudo fio $HOME/tools/FIO/NVME_128K_SR_Q128_5_15Min.fio'
                sh 'sudo fio $HOME/tools/FIO/NVME_4k_rand_qos.fio'
            }
        }

    } // end of stages list

} // end of the pipeline file
