pipeline{
  agent any
       stages{
         stage("checkout"){
           steps{
             echo "Checkoot SCM"
           }
         }
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
             input ('Do you want to continue result!!!')
             junit '**/target/surefire-reports/TEST-*.xml'
                    archive 'target/*.jar'
           }
         }
       }
}
