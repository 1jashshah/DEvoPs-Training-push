Day 14: In this task, I have done a set up of a CI/CD pipeline using Jenkins to streamline the deployment process of a simple Java application.
First of all, I created a simple application in Java as App.java which is given below:

package com.example;

public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}

![alt text](image-1.png)
javac App.java
java App.java
![alt text](image-2.png)
Secondly, I created a Dockerfile which which will create an image for this app.

FROM openjdk:11-slim
WORKDIR /app
COPY . /app
RUN javac App.java
CMD ["java", "App"]

Next, I created a Jenkinsfile which uses my GitHub repo to build the image from the Dockerfile, will push that docker image to my docker repository and make a comtainer out of that image.

pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git url:'https://github.com/1jashshah/Jenkins-java-docker-DAY14th-.git', branch: 'main'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t 1jashshah/day14th'
            }
        }
        stage('Push Docker Image') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerid')]) {
                    sh 'docker login'
                    sh 'docker push 1jashshah/day14th'
                }
            }
        }
        stage('Deploy Container') {
            steps {
                sh 'docker run -d -p 8089:8080 1jashshah/day14th'
            }
        }
    }
}