pipeline {
agent any
stages{
stage('clone my code'){
git 'https://github.com/deshamit/maven-project'
}
stage('compile my code'){
  steps {
  withMaven(mavan : 'localMaven'){
  sh 'mvn compile'
  }
  }
}
}
}
