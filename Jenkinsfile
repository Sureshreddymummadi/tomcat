pipeline{
    agent any
    stages {
       stage("scm"){
            steps{
                git credentialsId: 'git_credentials', url: 'https://github.com/jwala441/spring3-mvc-maven-xml-hello-world.git'
            }
       }
       stage("build"){
           steps{
           sh 'mvn package'
           }
       }
       stage("deploy"){
           steps{
           deploy adapters: [tomcat9(credentialsId: 'tomcat_credentials_pipeline', path: '', url: 'http://ec2-3-110-118-27.ap-south-1.compute.amazonaws.com:8181/')], contextPath: 'spring_pipeline', war: '**/target/*.war'           }
       }
       
    }
}
