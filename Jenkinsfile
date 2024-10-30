pipeline {
  /*
   * TODO: Implement pipeline stages/steps
   *   See documentation: https://www.jenkins.io/doc/book/pipeline/syntax/#stages
   */
   pipeline {
       agent any

       stages {
           stage('Build') {
               steps {
                   sh './gradlew assemble'
               }
           }
           stage('Test') {
               steps {
                   sh './gradlew test'
               }
           }
       }

       post {
           always {
               junit 'build/test-results/**/*.xml'
           }
           failure {
               echo 'Build or tests failed!'
           }
       }
   }
}
