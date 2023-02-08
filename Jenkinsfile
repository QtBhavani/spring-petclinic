node('JDK11') {
   stage('vcs') {
   git branch: 'REL', url: 'https://github.com/QtBhavani/spring-petclinic.git'
}                          
 stage("build"){
     sh 'mvn package'
 }
 stage("archive results"){
     junit'**surefire-reports/*.xml'   
 }
}