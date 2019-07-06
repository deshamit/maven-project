pipeline {
agent any
  tools {
        maven 'Maven 3.3.9'
        jdk 'jdk8'
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
sh 'mvn install'
  }
  } 
}
}
