pipeline {
    agent any
    triggers {
        pollSCM ''
    }
    stages {
        stage('Fetch data from Rfam database') {
            steps {
                sh 'mysql --user rfamro --host mysql-rfam-public.ebi.ac.uk --port 4497 --database Rfam < script.sql'
            }
        }
    }
}
