node('JDK11') {
   stage('vcs') {
   git branch: 'REL', url: 'https://github.com/QtBhavani/spring-petclinic.git'
}                          
 stage("build"){
     sh 'mvn package'
 }
 stage("archive results"){
      sh 'ln -s tests/test-results-unit.xml $WORKSPACE'
      junit "test-results-unit.xml"  
 }
}