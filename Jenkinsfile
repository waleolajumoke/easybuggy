pipeline{
    agent any 
    tools{
        maven "Maven_3_5_2"
    }
    stages{
        stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=tech365sec -Dsonar.organization=tech365sec -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=eb22cd1de47e6e77638d25db05e4069700253707'
			}
        } 
	  //   stage('RunSCAAnalysisUsingSnyk') {
   //          steps {		
			// 	withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
			// 		sh 'mvn snyk:test -fn'
			// 	}
			// }
   //  }	
//         stage('Build'){
//             steps{
//                 withDockerRegistry(
//                     [credentialsId:"dockerlogin", url: ""]
//                 )  {
//                     script{
//                     app = docker.build("asg")
//                     }
//                 }
//             }
//         }

//         stage('Push'){
//             steps{
//                 script{
//                     docker.withRegistry("https://601136829775.dkr.ecr.us-east-1.amazonaws.com", "ecr:us-east-1:aws-credentials"){
//                         app.push("latest")
//                     }
                    
                    
//                 }
//             }
//         }
    }

    
}
