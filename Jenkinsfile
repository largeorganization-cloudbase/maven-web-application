node{
    
    def mavenHome = tool name: "maven 3.8.5"


//checkout stage
 stage('checkout code'){
 git branch: 'development', url: 'https://github.com/largeorganization-cloudbase/maven-web-application.git'
}
//buid stage 
 stage('build stage'){
 sh "$mavenHome/bin/mvn clean package"
 }
 
 //sonarqube report generation
stage('sonar report'){
sh "$mavenHome/bin/mvn sonar:sonar "
}
//store artifactory repository
stage('store artifactery repo'){
sh "$mavenHome/bin/mvn deploy"
}
}
