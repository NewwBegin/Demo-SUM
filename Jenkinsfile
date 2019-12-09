node {
   stage("App build started") {
               git credentialsId: 'GithubID', url: 'https://github.com/NewwBegin/Demo-SUM.git' 
         }
     
   stage("Docker Build") {
              //sudo su
              sudo usermod -a -G docker jenkins
              docker.build "ashhh24/newsum" 
            }
   
   stage("Tag & Push image"){
         withDockerRegistry([credentialsId: 'dockerID',url: " "]) {
          sh 'docker tag ashhh24/newsum ashhh24/newsum:dev'
          sh 'docker push ashhh24/newsum:dev'
          sh 'docker push ashhh24/newsum:latest'       
         }
   }
}
