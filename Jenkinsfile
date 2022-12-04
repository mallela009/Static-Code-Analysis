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
                sh 'make check'
               
            }
        }
}
}
