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
                    app = docker.build("asg")
                    }
                }
            }
        }

        stage('Push'){
            steps{
                script{
                    docker.withRegistry("https://601136829775.dkr.ecr.us-east-1.amazonaws.com", "ecr:us-east-1:aws-credentials"){
                        app.push("latest")
                    }
                    
                    
                }
            }
        }
    }

    
}