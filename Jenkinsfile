pipeline{
agent any
stages{
stage("checkout"){
steps{
checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [],
 userRemoteConfigs: [[url: 'https://github.com/mallela009/Static-Code-Analysis.git']]])
}
}
stage('Build') { 
steps { 
       echo 'mvn clean install' 
            }
        }
stage('Test'){
            steps {
                echo 'mvn test'
               
            }
        }
 withSonarQubeEnv(installationName: ‘SonarQube-Server’, credentialsId: ‘SonarToken’) {
bat(script: ‘D://Softwares//sonar-scanner-cli//sonar-scanner-4.3.0.2102-windows//bin//sonar-scanner -Dproject.settings=sonar-project.properties’, label: ‘SonarQube Analysis’)
}
}
}
