properties([[$class: 'BuildDiscarderProperty',
                strategy: [$class: 'LogRotator', numToKeepStr: '10']],
                pipelineTriggers([[$class: 'GitHubPushTrigger'], pollSCM('H/15 * * * *')]),
                ])
pipeline {
    agent any
    stages {
        stage('Master Branch Deploy Code') {
            when {
                branch 'master'
            }
            steps {
                sh """
                echo "Building Artifact from Master branch"
                """

                sh """
                echo "Deploying Code from Master branch"
                """
            }
        }
        stage('Develop Branch Deploy Code') {
            when {
                branch 'feature-branch-1'
            }
            steps {
                sh """
                echo "Building Artifact from feature branch"
                """
                sh """
                echo "Deploying Code from feature branch"
                """
           }
        }
    }
}
