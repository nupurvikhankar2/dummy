pipeline{
  agent any
       stages{
         stage('build'){
           steps{
             bat 'mvn install'
         }
         }
         stage('package'){
           steps{
             bat 'mvn package'
           }
         }
           stage('test'){
             steps{
               bat 'mvn test'
             }
           }
         stage('Result'){
           steps{
             input ('Do you want to continue')
             junit '**/target/surefire-reports/TEST-*.xml'
                    archive 'target/*.jar'
           }
         }
       }
