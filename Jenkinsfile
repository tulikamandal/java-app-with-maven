node {
  stage('SCM first stage') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'MAVEN_HOME';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=MyMavenCode"
    }
  }
}
