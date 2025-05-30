pipeline {
    agent any
	environment {
        REPO_URL = "https://github.com/Abdulkhader081/ultimate-linux-guide.git"
    }

    stages {
        /*stage('Clone Repository') {
            steps {
                git url: "${REPO_URL}"
            }
        }*/

        stage('List Files') {
            steps {
		    sh """
                    pwd
                    ls -lrt
                    """
            }
        }
    }
}
