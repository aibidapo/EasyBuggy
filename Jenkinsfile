pipeline {
    agent {
        node {
            label 'maven'
        }
    }

environment {
    PATH = "/opt/apache-maven-3.9.6/bin:$PATH"
}   
    stages {
        stage("Build") {
            steps {
                sh 'mvn clean deploy'
            }
        }
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=ai-easybuggy -Dsonar.organization=ai-easybuggy -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=7ed004983bf02fccd1a14fd9e525be07f784d292'
			}
        } 
  }
}