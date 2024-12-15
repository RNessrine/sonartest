pipeline {
agent any
tools {
maven 'maven'
}
stages {
stage ("Clean up"){
steps {
deleteDir()
}
}
stage ("Clone repo"){
steps {
sh "git clone https://github.com/MaBouz/expl-spring.g
}
}
stage('Build') {
steps {
dir("exp1-spring"){
sh "mvn clean install"
}
}
}

  stage('SonarQube Analysis') {
     steps {
    withSonarQubeEnv('sonar-server') {
    dir("expl-spring"){
       sh 'mvn sonar:sonar'
        }
      }
}
}
}
}