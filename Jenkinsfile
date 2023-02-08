pipeline {
    agent { label 'JDK11' }
    parameters {
        choice(name: 'BRANCH_TO_BUILD', choices: ['main', 'REL', ], description: 'branch to be selected') 
        string(name: 'MAVEN_GOAL', defaultValue: 'package', description: 'build the package') }
   
    triggers {
         pollSCM('* * * * *') 
         }
    stages {
      stage('vcs') {
       steps { 
        git branch: "${params.BRANCH_TO_BUILD}", url: 'https://github.com/QtBhavani/spring-petclinic.git'
       } 
   } 
                           
     stage('build') {
            steps {
                sh "/usr/share/maven/bin/mvn ${params.MAVEN_GOAL}"
            }
        }
        stage('archive results') {
            steps {
                junit '**/surefire-reports/*.xml'
            }
        }
    }

}