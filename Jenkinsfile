node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'maven';
    withSonarQubeEnv() {
      bat "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=demo -Dsonar.projectName='demo' -Dsonar.host.url=http://localhost:9099"
      echo 'SonarQube Analysis Completed'
    }
  }
}
