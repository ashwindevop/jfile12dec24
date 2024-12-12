pipeline {
    agent any
    tools {
        maven "jenkin-maven"
    }   
        
    stages{
        stage('scm') {
            steps {
                git 'https://github.com/ashwindevop/mavenapp3war.git'
            }
        }
        stage('build') {
            steps {
             sh "mvn  clean  package"   
            }
        }
        stage('deploy to tomcat') {
            steps {
             sh ' scp /var/lib/jenkins/workspace/pipe9/target/app3.war  192.168.10.32:/opt/apache-tomcat-9/webapps '   
            }
        }
    }
}
