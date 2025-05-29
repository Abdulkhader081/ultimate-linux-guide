pipeline {
    agent any

    environment {
        REPORT_FILE = "branch_report.txt"
        REPO_URL = "https://github.com/Abdulkhader081/ultimate-linux-guide.git"
        EMAIL_ID = "abdulkhadermd081@gmail.com"
    }
	stages {
	        stage('Fetch Remote Branches') {
	            steps {
	                script {
	                    sh """
	                        echo "Branch List Report for ${REPO_URL}" > ${REPORT_FILE}
	                        echo "----------------------------------------" >> ${REPORT_FILE}
	                        git ls-remote --heads ${REPO_URL} | awk '{print \$2}' | sed 's|refs/heads/||' >> ${REPORT_FILE}
	                    """
	                }
	            }
        	}
	}
	}
