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
/**
node{
    checkout scm
    def pp
    stage('init'){
        def userInput = input(
            id: 'userInput', message: 'Let\'s promote?', parameters: [
            [$class: 'TextParameterDefinition', defaultValue: 'uat', description: 'Environment', name: 'env']
        ])
echo ("Env: "+userInput)
        pp='fin'
    }
    stage('Build') {
        withMaven(maven:'Maven Test'){
           sh 'mvn clean compile'
        }
    }
    stage('Test') {
           withMaven(maven:'Maven Test'){
                sh 'mvn test'
            }
            
                
    }
    stage('Deploy') {
            withMaven(maven:'Maven Test'){
                sh 'mvn package'
            }
                
    }
    stage('Copy Files'){
        fileOperations([fileCopyOperation(includes: '** /*.jar', targetLocation: '/home/ivan/dist')])
       
    }
    stage('Delete Workspace'){
        
        deleteDir()
    }
    stage('end'){
        echo (pp)
    }
}
***/
node {
    try {
        stage('Test') {
            sh 'echo "Fallo!"; exit 0'
        }
        echo 'Se ejecuta si exito'
    } catch (e) {
        echo 'Se ejecuta si fallo'
        throw e
    } finally {
        
        def currentResult = currentBuild.result?.result : 'FAILURE'
        if (currentResult == 'FAILURE') {
            echo 'Se ejecuta si FAILURE'
        }
        echo  currentResult
        
        def previousResult = currentBuild.previousBuild?.result
        if (previousResult != null && previousResult != currentResult) {
            echo 'Se ejecuta si hay cambio de estado'
        }
       
        echo previousResult
        echo 'Se ejecuta siempre'
    }
}
