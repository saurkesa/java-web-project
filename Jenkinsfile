pipeline{
    agent any
    stages{
        stage('build'){
            steps{
                sh 'mvn clean install'
            }
        }
        stage('deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: '291d70d1-c12a-4407-8ac5-e432cea69af2', path: '', 
                url: 'http://ec2-18-205-239-20.compute-1.amazonaws.com:8080/')],
                contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
