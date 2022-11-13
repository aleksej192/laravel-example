pipeline {
    agent any

    options {
        buildDiscarder(
            logRotator(
                artifactDaysToKeepStr: "1",
                artifactNumToKeepStr: "1",
                daysToKeepStr: "1",
                numToKeepStr: "1"
            )
        )
        disableConcurrentBuilds()
    }

    stages {

        stage('Build backend') {
            when {
                branch 'main'
            }

            steps {
                sh 'dep deploy prod -vv'
            }
        }
    }
}
