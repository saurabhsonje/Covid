node{
      
      stage('Checkout'){
         git 'https://github.com/LovesCloud/java-tomcat-maven-example'
       
      }  
      def mvnHome = tool 'M3
      stage('Build'){
         //// Get maven home path and build
        
        //def mvnHome = tool 'M3'
        sh "${mvnHome}/bin/mvn clean package -Dmaven.test.skip=true"
      }
     
      stage('Deploy') {     
            sshagent(['Tomcat-jenkins']) {
               sh 'scp -o StrictHostKeyChecking=no target/tomcatdeploymnetdemo.war saurabh@54.163.29.126:usr/share/nginx/html'
              
          }
         
     }
      
 }
