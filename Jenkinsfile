pipeline {
    agent any

    stages {
        stage('Setup') {
            steps {
                sh './RUN_THIS.py'
                sh 'TMP=~/.cache/NuGet/ nuget restore'
            }
        }
        stage('Build') {
            steps {
                sh './package_release_build.py'
                archiveArtifacts artifacts: 'release/*.zip'
                archiveArtifacts artifacts: 'engine/Resources/ResourcePack.zip'
            }
        }
    }
}
