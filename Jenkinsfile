def installTerraform() {
    // Check if terraform is already installed
    def terraformExists = sh(script: 'which terraform', returnStatus: true)
    if (terraformExists != 0) {
        // Install terraform
        sh '''
            echo "Installing Terraform..."
            wget https://releases.hashicorp.com/terraform/1.0.0/terraform_1.0.0_linux_amd64.zip
            unzip terraform_1.0.0_linux_amd64.zip
            sudo mv terraform /usr/local/bin/
            rm -f terraform_1.0.0_linux_amd64.zip
        '''
    } else {
        echo "Terraform already installed!"
    }
}

pipeline {
    agent any

    stages {
        stage('Install Terraform') {
            steps {
                script {
                    installTerraform()
                }
            }
        }
       stage('Creating EC2 instance'){
	steps {
            script {
		sh 'echo "Creating EC2 instance"'
		}
	     }
	}
    }
}

