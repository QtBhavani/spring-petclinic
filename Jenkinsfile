node('jdk11') {
   stage('vcs') {
   git branch: 'REL', url: 'https://github.com/QtBhavani/spring-petclinic.git'
}
 stage("build"){
     sh '/opt/apache-maven-3.6.3/bin/mvn package'
 }
 stage("archive results"){
     junit'**surefire-reports/*.xml'   
 }
}