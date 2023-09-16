pipeline {
    agent any
    //def image-vote
    //def image-result
    //def image-worker
    tools {
        nodejs 'NodeJS 20.6.1'
    }
    environment 
   { 
       // replace xyz with the copy pasted iD
       //GitHubUser = credentials('00759f27-a2d5-474d-92d6-ffe34bd19922')  
   }
    stages {
        stage('Versions')
        {
            steps {
                sh 'node --version'
                sh 'python3 --version'
            }
        }
        stage('Clone de l\'application depuis Git')
        {
            steps {
                //sh 'rm -rf /example-voting-app'
                //git clone 'git@github.com/crj1035/example-voting-app.git'
                script {
                    git branch: 'main',
                        credentialsId: '00759f27-a2d5-474d-92d6-ffe34bd19922',
                        url: 'https://github.com/crj1035/example-voting-app.git'
                }
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

