pipeline {
    agent none 
    stages {
        stage('scm checkout') {
            agent { docker 'maven:master' } 
            steps {
                git branch: 'master', url: 'https://github.com/shubhampareek1513/gradle-calculator.git'
                sh 'mvn --version'
            }
        }
        stage('validate code') {
            agent { docker 'gradle:slave1' } 
            steps {
                withGradle {jdk: 'localjdk', gradle: 'localgradle'
  
                             }
            }
        }
    }
}
