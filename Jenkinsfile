node {
    def EMAIL_ID = params.emailID
    def REPO_URL = params.gitURL
    def REPORT_FILE = 'branches.txt'


    stage('Fetch Remote Branches') {
        sh """
            echo "Branch List Report for ${REPO_URL}" > ${REPORT_FILE}
            echo "----------------------------------------" >> ${REPORT_FILE}
            git ls-remote --heads ${REPO_URL} | awk '{print \$2}' | sed 's|refs/heads/||' >> ${REPORT_FILE}
        """
    }

    stage('Send Email') {
        emailext(
            to: EMAIL_ID,
            subject: "Git Branch Report",
            body: """\
                Please find the attached branch list for repository: ${REPO_URL}
                Regards,
                Jenkins
            """,
            attachmentsPattern: REPORT_FILE
        )
    }
}
