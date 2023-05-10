pipeline {
   agent any
   tools {
      maven 'Maven'
      jdk 'JDK'
   }

   stages {
      stage('Initialize'){
         steps {
            sh ''' 
                  echo "PATH = $(PATH)"
                  echo "JAVA_HOME = $(JAVA_HOME)"
                  echo "MAVEN_HOME = $(MAVEN_HOME)"
                  '''
          }
      }
      stage('Build') {
         steps {
            // Run Maven on a Unix agent.
            sh "mvn clean package"
         }
      stage('Test') {
         steps {
            echo "Test"
            sh 'mvn test'
         }
      }
      stage('Package'){
         steps {
            echo 'PACKAGE'
            sh 'mvn clean package -DskipTests=true'
         }
      }
      stage('Deploy'){
         steps {echo 'DEPLOY'}
      }
      }
   }
}
