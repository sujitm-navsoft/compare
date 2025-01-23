pipeline {
    // environment {
    //     JAVA_HOME = "/usr/lib/jvm/java-17-openjdk-amd64"
    //     PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
    // }
    agent any
    stages {
        
      

        stage('Sonarqube scan') {
            steps {
                script {
                    scannerHome = tool 'sonar-scanner'
                }
                withSonarQubeEnv('sonarqube') {
                    sh "${scannerHome}/bin/sonar-scanner sonar.projectKey=my_project sonar.sources=. sonar.host.url=http://sonar:9000 sonar.token=squ_0bf674ad67f35a6f34df9cd1043defae762f3f35"
                }
                // script {
                //     scannerHome = tool 'sonar-scanner'
                // }
                // withSonarQubeEnv('sonarqube') {
                //     sh "${scannerHome}/bin/sonar-scanner -X"
                // }
            }
        }
        
        // stage('Quality Gate') {
        //     steps {
        //         withSonarQubeEnv('sonarqube') {
        //             waitForQualityGate abortPipeline: true
        //         }
        //     }
        // }
        
      
    }
}
