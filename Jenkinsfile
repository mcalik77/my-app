library identifier: 'jenkins-library@master', retriever: modernSCM([$class: 'GitSCMSource', credentialsId: '', remote: 'git@github.com:mcalik77/jenkins-shared-library.git'])
pipeline {
    agent any
    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven"
    }
    stages {
         stage('Git CheckOut') {
            steps {
            gitCheckout(
                branch: "master",
                url: "https://github.com/mcalik77/my-app.git"
            )
            }
        }
        
        stage('---clean---') {
            steps {
                sh "mvn clean"
            }
        }
        stage('--test--') {
            steps {
                sh "mvn test"
            }
        }
        stage('--package--') {
            steps {
                sh "mvn package"
            }
        }
    }
}
