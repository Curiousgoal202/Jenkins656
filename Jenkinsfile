pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Curiousgoal202/Jenkins656.git'
            }
        }

        stage('Deploy the Server') {
            steps {
                sh '''
                # Kill old server if running
                pkill -f "python3 -m http.server" || true

                # Go to Jenkins workspace
                cd "$WORKSPACE"

                # Start new Python web server on port 8085
                python3 -m http.server 8085 
                 '''
            }
        }
    }
}
