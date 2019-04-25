pipeline {
    agent { docker 'maven' }
    stages{
        stage('checkout'){
            steps{
                git 'https://github.com/subhash1992/spring-petclinic.git'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn clean package'
                junit '**/target/surefire-reports/TEST-*.xml'
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
