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
        stage ('Flutter Doctor') {
            steps {
                sh "flutter doctor -v"
            }
        }
        stage('Get Dependencies'){ 
            steps{
                sh"flutter pub get" 
            }
        } 
        stage('Build'){
            steps{
                sh"${env.SOURCE}; flutter build apk --release --no-sound-null-safety"
            }
        }
        stage('Upload'){
            steps{
                sh"Uploading the apk file to the server..."
            }
        } 
    }
}
