pipeline{
    agent{
        node{
            label 'local-docker-agent'
        }
    }
    stages{
        stage('Build'){
            steps{
                sh '''
                    pip install -r requirements.txt
                '''
            }
        }
        stage('Test'){
            steps{
                sh '''
                    python3 --version
                    if [ -e hello.py ]
                    then
                        echo "All Good!"
                    else
                        echo "Python script missing!"
                    fi
                '''
            }
        }
        stage('Deliver'){
            steps{
                sh '''
                python3 hello.py
                '''
            }
        }
    }
}