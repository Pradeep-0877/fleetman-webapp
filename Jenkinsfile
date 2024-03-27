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
         post{
            success{
               archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
            }
         }
      }
      stage("Test"){
         steps{
            sh "mvn test"
         }
         post{
            success{
               junit stdioRetention: '', testResults: 'target/surefire-reports/*.xml'
            }
         }
      }
   }

}