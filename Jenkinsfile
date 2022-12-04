pipeline {
    agent any
    stages {
        stage('SCM') {
            steps {
                git url: 'https://github.com/mallela009/Static-Code-Analysis.git'
            }
        }
        stage('build && SonarQube analysis') {
            steps {
                withSonarQubeEnv('SONAR_RUNNER_HOME') {
                    // Optionally use a Maven environment you've configured already
                    withMaven(maven:' Maven 3.6.3') {
                        sh 'mvn clean package sonar:sonar'
                    }
                }
            }
        }
