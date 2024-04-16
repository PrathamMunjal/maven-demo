node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'maven';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=demo -Dsonar.projectName='demo' -Dsonar.host.url=http://192.168.1.222:9099"
      echo 'SonarQube Analysis Completed'
    }
  }
}
