pipeline{
   agent {
    docker {
      image 'maven:3.6.3-jdk-11'
      args '-v /root/.m2:/root/.m2'
    }
  }
  stages {
      stage("Maven Build"){
          steps{
            sh 'mvn -B -DskipTests clean package'
             
          }
        
      }
  }
      stage('Maven Test'){
            steps{
              sh 'mvn test'
            }
            post{
            always{
                junit 'target/surefire-reports/*.xml'
            }
        }
        }
  
    }
    
