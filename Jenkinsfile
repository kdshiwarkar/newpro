pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'mvn install'
            }
        }
        stage('Deployment') {
            steps {
                sh 'cp target/newpro.war /home/kunalshiwarkar/Documents/Devops_software/tar/apache-tomcat-9.0.89/webapps'
            }
        }
        stage('docker build') {
            steps {
                sh 'docker build -t kunalsh/kunal:latest .'
            }
        }
        stage('Container creation') {
            steps {
                sh 'docker run -it -d --name=container_new2 kunalsh/kunal:latest /bin/bash'
            }
        }
          }}
