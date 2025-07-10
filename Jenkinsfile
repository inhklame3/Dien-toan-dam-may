   pipeline {
       agent any
       stages {
           stage('Clone') {
               steps {
                  git branch: 'main', url: 'https://github.com/inhklame3/Dien-toan-dam-may.git'
               }
           }
           stage('Build Docker Image') {
               steps {
                   script {
                       dockerImage = docker.build("flask-cicd-demo")
                   }
               }
           }
           stage('Run Container') {
               steps {
                   script {
                       dockerImage.run("-d -p 5000:5000")
                   }
               }
           }
       }
   }
