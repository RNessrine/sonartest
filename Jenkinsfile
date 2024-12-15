
pipeline {
  agent any
  tools {
    maven 'Maven 3.8.6' // Remplacez par le nom exact configuré dans Jenkins
  }
  stages {
    stage("Clean up") {
      steps {
        deleteDir()
      }
    }
    stage("Clone repo") {
      steps {
        sh "git clone https://github.com/RNessrine/sonartest.git"
      }
    }
    stage("Generate backend image") {
      steps {
        dir("exp1-spring") { // Utilisez "exBackend" si le pom.xml est dans ce dossier
          sh "mvn clean install"
             sh "docker build -t docexp1-spring ."

          
        }
      }
    }
    stage("Run docker compose") {
     steps {
 
    dir("expl-spring"){
       sh "docker compose up -d"
        }
      }
    }
  }
}


