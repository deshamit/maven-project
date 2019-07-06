pipeline {
agent any
  tools {
        maven 'localMaven'
        jdk 'localJava'
    }
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
stage('test'){
steps {
withMaven(maven :'localMaven'){
sh 'mvn test'
  }
  }
}
stage('package'){
steps {
withMaven(maven :'localMaven'){
sh 'mvn package'
  }
  }
}
stage('install'){
steps {
withMaven(maven :'localMaven')
sh 'mvn clean install'
  }
  } 
}
}
