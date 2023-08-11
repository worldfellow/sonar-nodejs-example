
node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv("sonarqube-scanner") {
      sh "${scannerHome}/bin/sonar-scanner \
     -Dsonar.projectKey=sonar-example \
                 -Dsonar.sources=. \
                 -Dsonar.css.node=. \
                 -Dsonar.host.url=http://161.97.98.103:9000/"
    }
  }
}

