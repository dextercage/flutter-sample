pipeline{
    //This line is to tell Jenkins which agent should run the pipeline
    agent { label 'flutter' } 
    stages{
        stage('Fetch'){ 
            steps{
                sh"${env.SOURCE}; flutter pub get" 
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
