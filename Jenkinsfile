pipeline {
    agent {
        node {
            label 'maven'
        }
    }
    stages {
        stage('Tests'){
            steps {
                sh './mvnw clean test'
            }
        }
        stage('package'){
            steps {
                sh '''
                    ./mvn package -DskipTests \
                    -Dquarkus.package.type=uber-jar
                '''
                archiveArtifacts 'target/*.jar'
            }
        }
    }
}