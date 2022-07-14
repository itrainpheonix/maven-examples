node {
   
   stage('Code checkout') { // for display purposes
     git credentialsId: 'github-mani-id', url: 'https://github.com/thanos-devops-berlin/maven-examples.git'  
   }
   stage('Build') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
      sh 'mvn clean compile'
    } 
   }
   stage('Test') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
      sh 'mvn test'
    }
   }
  stage('Code Analysis') {
   withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
      sh 'mvn clean verify sonar:sonar -Dsonar.login=6aebe04f8465fac27f4dd28744d56a7f4a82d21c'
    }
    
   }
   stage('Package') {
   
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
      sh 'mvn package'
    }
   }
   stage('Deploy to Dev') {
   
    
   }
   
} 
   
