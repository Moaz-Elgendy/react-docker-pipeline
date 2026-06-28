pipeline {
    agent{
        label 'docker'
    }

    stages {
        
        stage('build from a docker file'){
            steps{
                scripts{
                    sh 'docker build -t mk0230/docker-react -f Dockerfile.dev .'
                }
            }
        }
        stage('run tests'){
            steps{
                script{
                    env.DOCKER_BUILDKIT = 1
                    sh 'docker run -e CI=true mk0230/docker-react npm run start'
                }
            }
        }
        

    }




}