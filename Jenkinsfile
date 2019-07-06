pipeline {
agent any
stages{
stage('clone my code'){
  steps{
git 'https://github.com/deshamit/maven-project'
  }
}
stage('compile my code'){
  steps {
  withMaven(maven : 'localMaven'){
  sh 'mvn compile'
  }
  }
}
}
}
