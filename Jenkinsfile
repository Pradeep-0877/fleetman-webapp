pipeline{
   agent any
   tools{
      maven "my-maven"
      jdk 'java-17'
   }
   stages{
      stage("Build"){
         steps{
            sh "mvn package -DskipTests=true"
         }
      }
      stage("Test"){
         steps{
            sh "mvn test"
         }
      }
   }

}