pipeline{
    agent {label "dev"};
    stages{
        stage("code"){
            steps{
                git url: "https://github.com/Deepak8260/Flask-1-tier-app.git", branch: "main"
                echo "Git Clone Ho gaya successfully"
            }
        }
        stage("cleanup old image"){
            steps{
                sh "docker rmi flask-app:latest || true"
                sh "docker rmi kumar3472/flask-single-tier:latest || true"
            }
        }
        stage("build"){
            steps{
                sh "docker build -t flask-app:latest ."
                echo "Docker build Ho gaya successfully"
            }
        }
        stage("push to dockerhub"){
            steps{
                withCredentials([
                usernamePassword(credentialsId:"dockerHubCreds", 
                usernameVariable:"dockerHubUser" , 
                passwordVariable: "dockerHubPass")
                ]){
                sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                sh "docker image tag flask-app ${env.dockerHubUser}/flask-single-tier"
                sh "docker push ${env.dockerHubUser}/flask-single-tier:latest"
                
                    
                }
            }
        }
        stage("deploy"){
            steps{
                sh "docker stop my-flask-app || true"
                sh "docker rm my-flask-app || true"
                sh "docker run -d -p 5000:5000 --name my-flask-app flask-app:latest"
                echo "deploy ho gaya"
            }
        }
    }
}
