pipeline {
    agent any

    tools {
        maven "mavenTool"
    }

    stages {
        stage('Build') {
            steps {
                git 'https://github.com/morgom94/simple-java-maven-app.git'
                bat "mvn  clean package"
            }
        }
        stage('Test Jar Package') {
            steps {
                bat 'java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App'
            }
        }
        stage('Verify package') {
            steps {
                bat 'mvn verify'
            }
        }
    }
}
