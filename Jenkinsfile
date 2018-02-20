pipeline {
  agent any
  stages {
    stage('Compania 1') {
      parallel {
        stage('Compania 1') {
          steps {
            output1 = bat(script: 'sqlcmd -S server-central -U sa -P sql_2016 -d DBeDocSys2014 -i C:\\Users\\usuario1\\Desktop\\test.sql', returnStdout: true)
		  }
        }
        stage('Compania 2') {
          steps {
            bat(script: 'sqlcmd -S server-central -U sa -P sql_2016 -d DBeDocSys2014 -i C:\\Users\\usuario1\\Desktop\\test2.sql', returnStdout: true)
          }
        }
      }
    }
  }
  post {
    success {
      mail(bcc: '', body: "Run ${JOB_NAME}-#${BUILD_NUMBER} succeeded. To get more details, visit the build results page: ${BUILD_URL}.", cc: '', from: 'jenkins-admin@gmail.com', replyTo: '', subject: "${JOB_NAME} ${BUILD_NUMBER} succeeded ", to: 'mig.suarez1989@gmail.com')
      
    }
    
    failure {
      mail(bcc: '', body: "Run ${JOB_NAME}-#${BUILD_NUMBER} succeeded. To get more details, visit the build results page: ${BUILD_URL}.", cc: '', from: 'jenkins-admin@gmail.com', replyTo: '', subject: "${JOB_NAME} ${BUILD_NUMBER} failed", to: 'mig.suarez1989@gmail.com')
      
    }
    
  }
}