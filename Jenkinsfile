pipeline{
    agent any 
    stages{
        stage('Build'){
            steps{
                echo "Building the code with Gradle..."
                sleep 5
                echo "Build complete!"
            }
        }
        stage('Test'){
            steps{
                echo "Unit Tests running on JUnit..."
                echo "Integration Testing on Selenium..."
                echo "Testing complete!"
            }
            post{
                success {
                    mail to: "rahulprem90@gmail.com",
                    subject: "Jenkins Testing Status",
                    body: "Dear Developer, all your unit and integration tests were successful! Please find logs attached to this email"
                    attachLog: true
                }
            }
        }
        stage('Code Analysis'){
            steps{
                echo "Analysing the code with CodeClimate..."
                echo "Code Analysis complete!"
            }
        }
        stage('Security Scan'){
            steps{
                echo "Scanning the code with Fortify..."
                echo "Security Scan complete!"
            }
            post{
                success {
                    mail to: "rahulprem90@gmail.com",
                    subject: "Jenkins Security Scan",
                    body: "Dear Developer, your Security Scan was completed successfully! Please find logs attached to this email"
                    attachLog: true
                }
            }
        }
        stage('Deploy to Staging'){
            steps{
                echo "Deploying to GCP Compute Engine Instance..."
                sleep 2
                echo "Deployment complete!"
            }
        }
        stage('Integration Tests on Staging'){
            steps{
                echo "Running Integration Tests on GCP Compute Engine Instance using Cypress..."
                echo "Integration tests complete!"
            }
        }
        stage('Deploy to Production'){
            steps{
                echo "Deploying Application to Oracle Cloud..."
                sleep 5
                echo "Deployment complete!"
            }
        }
    }
}
