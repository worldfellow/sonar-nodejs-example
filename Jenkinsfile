
node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv("sonarqube-scanner") {
      sh "${scannerHome}/bin/sonar-scanner \
     sonar-scanner \
       -Dsonar.projectKey=sonar-example \
       -Dsonar.sources=. \
       -Dsonar.host.url=http://164.68.101.124:9000 \
       -Dsonar.login=39514bf8b747fe346041b0de86fd9ece88f71ea5
    }
  }
}
