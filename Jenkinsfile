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
                sh"pwd && ls -larth && flutter build apk"
            }
        }
        stage('Upload'){
            steps{
                echo "Uploading the apk file to the server..."
                sh"pwd && ls -larth"
            }
        } 
    }
}
