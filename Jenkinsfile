pipeline {
    agent any
    tools {
        nodejs 'NodeJS 20.6.1'
    }
    stages {
        stage('Build')
        {
            steps {
                sh 'echo arrivé jusque là'
                //sh 'npm '
            }
        }
        /*
        stage('Generate')
        {
            steps {
                sh 'mvn generate-test-resources process-test-resources'
            }
        }
        */
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

