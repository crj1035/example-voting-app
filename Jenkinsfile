node {
    def imgvote
    def imgresult
    def imgworker
    agent any
    
    tools {
        nodejs 'NodeJS 20.6.1'
    }
    // Credentials 00759f27-a2d5-474d-92d6-ffe34bd19922 
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
                script {
                    // Connexion à Github
                    git branch: 'main',
                        credentialsId: '00759f27-a2d5-474d-92d6-ffe34bd19922',
                        url: 'https://github.com/crj1035/example-voting-app'
                    // Suppression de tout le réperoire s'il existe
                }
                sh 'cd .. & rm -rf example-voting-app'
                sh 'git clone https://github.com/crj1035/example-voting-app.git'
            }
        }
        stage('Build des 3 images') {
            imgvote = docker.build(crj1035/example-voting-vote)
            imgresult = docker.build(crj1035/example-voting-result)
            imgworker = docker.build(crj1035/example-voting-worker)
        }
/*        stage('Test image') {
            docker.image('crj1035/example-voting-app').withRun('-p 20000:5000')
        }
 */
        /*
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

