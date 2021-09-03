pipeline {
    agent any
    tools {    
        maven "maven-3.6.2"
    }
    stages {
        stage('Build') {
            steps {
                git 'https://github.com/ShwetKetu/jenkin-job.git'
                sh "mvn -s setting.xml -Dmaven.test.failure.ignore=true clean deploy"
            }
            post {  
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}
