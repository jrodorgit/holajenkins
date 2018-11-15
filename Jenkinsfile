#!/usr/bin/env groovy
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
        withMaven(maven:'Maven Test'){
           sh 'mvn clean compile'
        }
    }
    stage('Test') {
           sh 'mvn test'
                
    }
    stage('Deploy') {
           sh 'mvn package'
                
    }
}
