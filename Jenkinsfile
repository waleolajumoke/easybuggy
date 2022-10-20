pipeline{
    agent any 
    tools{
        maven "Maven_3_5_2"
    }
    stages{
        stage('Build'){
            steps{
                withDockerRegistry(
                    [credentialsId:"dockerlogin", url: ""]
                )  {
                    script{
                    app = docker.build("tech365easybuggy")
                    }
                }
            }
        }

        stage('Push'){
            steps{
                script{
                    docker.withRegistry("https://601136829775.dkr.ecr.us-west-1.amazonaws.com", "ecr:us-west-1:aws-credentials")
                    app.push("latest")
                    
                }
            }
        }
    }

    
}