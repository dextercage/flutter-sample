pipeline {
    agent { 
        dockerContainer {
            image 'growerp/flutter-sdk-image'
        }
      }
    triggers {
        pollSCM '*/3 * * * *'
    }
    stages{
        stage('Get Dependencies'){ 
            steps{
                sh"flutter pub get" 
            }
        } 
        stage('Build'){
            steps{
                sh"flutter build apk"
            }
        }
        stage('Upload'){
            steps{
                sh"Uploading the apk file to the server..."
            }
        } 
    }
}
