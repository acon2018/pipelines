pipeline {
  agent any
  stages {
    stage('Testing db') {
      steps {
        bat 'sqlcmd -S server-central -U sa -P sql_2016 -d DBeDocSys2014 -i Desktop/test.sql'
      }
    }
  }
}