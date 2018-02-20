pipeline {
  agent any
  environment {
    RESULT_1 = ""
	RESULT_2 = ""

  }
  stages {
    stage('Companias') {
      parallel {
        stage('Compania 1') {
          steps {
		   script{
		   
           def output1 =bat(script: 'sqlcmd -S server-central -U sa -P sql_2016 -d DBeDocSys2014 -i C:\\Users\\usuario1\\Desktop\\test.sql', returnStdout: true)
		   RESULT_1 = output1.trim()
		    }
			echo "${RESULT_1}"
		   }
        }
        stage('Compania 2') {
          steps {
		    script{
            def output2 = bat(script: 'sqlcmd -S server-central -U sa -P sql_2016 -d DBeDocSys2014 -i C:\\Users\\usuario1\\Desktop\\test2.sql', returnStdout: true)
            RESULT_2 = output2;
		  }
		  echo "${RESULT_2}"
        }
      }
	  }
    }
  }
  post {
    success {
      mail(bcc: '', body: "Run ${JOB_NAME}-#${BUILD_NUMBER} succeeded. To get more details, visit the build results page: ${BUILD_URL}.\n\n COMPANIA 1: ${RESULT_1} \n\n COMPANIA 2: ${RESULT_2}", cc: '', from: 'jenkins-admin@gmail.com', replyTo: '', subject: "${JOB_NAME} ${BUILD_NUMBER} succeeded ", to: 'mig.suarez1989@gmail.com')
      
    }
    
    failure {
      mail(bcc: '', body: "Run ${JOB_NAME}-#${BUILD_NUMBER} succeeded. To get more details, visit the build results page: ${BUILD_URL}.", cc: '', from: 'jenkins-admin@gmail.com', replyTo: '', subject: "${JOB_NAME} ${BUILD_NUMBER} failed", to: 'mig.suarez1989@gmail.com')
      
    }
    
  }
}