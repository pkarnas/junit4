pipeline {
   agent any
   options {
    ansiColor('xterm')
    timestamps()
   }
   post{
       always{
         junit '**/target/surefire-reports/*.xml'
       }
    }
   stages {
       stage('Stage 1 download') {
            steps {
                git branch: 'mavenWrapper', poll: false, url: 'https://github.com/pkarnas/junit4.git'
            }
      }
      stage('Stage 2 run maven') {
         steps {
            sh './mvnw clean verify'
         }
      }
   }
}