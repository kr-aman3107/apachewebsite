pipeline{
    agent any
    stages{
       stage('Clone Repository'){
            steps{
                 git 'https://github.com/kr-aman3107/apachewebsite.git'
            }
       }
            stage('Deploy to Apache Server'){
                steps{
                    script{
                        sh""
                        sudo rm -rf/var/wwwhtml/ *
                        sudo cp -r* /var/www/html/
                        sudo chown -R www-data:www-data /var/www/html/
                        sudo chmod -R 755/var/www/html/
                        ""
                    }
                }
            }
            stage('Restart Apache'){
                steps{
                    script{
                        sh 'sudo systemctl restart apache2'
                    }
                }
            }
    }
    post{
        success{
            echo 'Deployment SuccessFull! Website is live on apache.'
        }
        failure{
            echo 'Deployement Failed!'
        }
    }
}
