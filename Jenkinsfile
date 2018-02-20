pipeline {
  agent any
  stages {
    stage('Compania 1') {
      steps {
        bat 'sqlcmd -S server-central -U sa -P sql_2016 -d DBeDocSys2014 -i C:\\Users\\usuario1\\Desktop\\test.sql'
      }
    }
  }
}