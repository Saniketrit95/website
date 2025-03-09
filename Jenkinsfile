pipeline {
    agent any

    stages {
        stage('Pull Code') {
            steps {
                script {
                    def targetFolder = "/var/www/develop"
                    
                    // Ensure the folder exists
                    sh "mkdir -p ${targetFolder}"

                    // Clone or pull the latest code
                    sh """
                        if [ -d "${targetFolder}/.git" ]; then
                            cd ${targetFolder}
                            git pull origin develop
                        else
                            rm -rf ${targetFolder}
                            git clone -b develop https://github.com/Saniketrit95/website.git ${targetFolder}
                        fi
                    """
                }
            }
        }
    }
}
