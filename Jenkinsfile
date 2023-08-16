pipeline {
    agent { label 'shell' }

    // environment {
    //     // AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
    //     // AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
    // }

    stages{

        stage('Git Checkout'){

            steps{
                git branch: 'main', url: 'https://github.com/Project2700/counter-app.git'
            }
            
        }
        stage('UNIT Testing'){

            steps{
                sh 'mvn test'
            }
            
        }
        stage('Integration Testing'){

            steps{
                sh 'mvn verify -DskipUnitTests'
            }
            
        }
        stage('Building Maven'){

            steps{
                sh 'mvn clean install'
            }
            
        }

    }        
}

// webhook ip adresi değişecek
// ssh public ip değişecek
// jenkins agent ip değişecek