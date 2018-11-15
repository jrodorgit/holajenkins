/* sintaxis declarativa 
pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps{
                echo 'building.....'
                sh 'mvn package'
                
            }
        }
        stage('Test') {
            steps{
                echo 'testing....'
            }
        }
        stage('Deploy') {
            steps{
                echo 'deploying....'
            }
        }
    }
    
}
*/
node{
    checkout scm
    
    stage('Build') {
           
                echo 'building...'
                withMaven(
                    // Maven installation declared in the Jenkins "Global Tool Configuration"
                    maven: 'Maven Test'
                ) 
 
                // Run the maven build
                sh "mvn clean test"
    }
}
