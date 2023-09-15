pipeline {
    agent any
    //def image-vote
    //def image-result
    //def image-worker
    tools {
        nodejs 'NodeJS 20.6.1'
    }
    stages {
        stage('Versions')
        {
            steps {
                sh 'node --version'
                sh 'python3 --version'
                sh 'echo arrivé jusque là'
            }
        }
        stage('Compilation de vote')
        {
            steps {
                sh 'npm /home/christophe/Documents/fil-rouge/example-voting-app/vote'
                sh 'compilation terminée'
            }
        }
        
        /*
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true -DtestFailureIgnore=true test'
            }
        }
        stage('Generate Jar') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true -DtestFailureIgnore=true package'
            }
        }
        stage('Process build') {
               parallel {
                    stage('Artifact Jar') {
                        steps {
                            archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
                        }
                    }
                    stage('Process Test reports') {
                        steps {
                            junit checksName: 'Jenkins Junit Tests', skipMarkingBuildUnstable: true, testResults: 'target/surefire-reports/*.xml'
                        }
                    }
               }
        }
        */
    }
}

