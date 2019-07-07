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
withMaven(maven :'localMaven'){
sh 'mvn install'
}
}
}
stage('deploy to tomcat'){
steps{
  sshagent (credentials: ['3293f1b1-8fb4-41a6-b6d6-1910c1ffbb21']) {
    sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@13.233.113.159:/usr/share/tomcat/webapps'
}
}
}
}
}
