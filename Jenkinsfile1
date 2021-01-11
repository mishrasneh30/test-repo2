pipeline {
   agent {
       docker {
           image 'maven:3.6.0-jdk-8-alpine'
           args '-u root'
       }
   }
   environment {
      
       BDS_JAVA_HOME="/usr/lib/jvm/java-1.8-openjdk"
   }
   stages {
       stage('Run Synopsys Detect') {
           steps {
              
               git 'https://github.com/mishrasneh30/test-repo2.git'
               
               sh "mvn clean install"
               
                synopsys_detect detectProperties: '--detect.project.name="Declarative_Pipeline_Docker_1827013740_3" --detect.excluded.detector.types=GIT'
                         
                  }
              
           }
       }
   }

