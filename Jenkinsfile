node('master') {
  checkout scm
  
  stage('Build') {
    withMaven(jdk: 'JDK8', maven: 'M3') {
      sh 'mvn -Dmaven.test.failure.ignore clean package'
    }
  }
  
  stage('Restuls') {
    junit '**/target/surefire-reports/TEST-*.xml'
    archive 'target/*.jar'
  }
}
