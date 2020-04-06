node{
      def mvnHome
      stage('Checkout'){
         git 'https://github.com/LovesCloud/java-tomcat-maven-example'
           mvnHome = tool 'MAVEN3'
           echo "checkout down "
       
      }  
      //def mvnHome = tool 'M3'
      stage('Build'){
      
           
         //// Get maven home path and build
        //def mvnHome = tool 'M3'
        //sh "${mvnHome}/bin/mvn clean package -Dmaven.test.skip=true"
       // sh "${mvnHome}/bin/mvn clean package -Dmaven.test.skip=true"
         //sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
         sh "${mvnHome}/bin/mvn package"   
           echo "build down "
        
      }
      
      stage ('Test-JUnit'){
         // sh "'${mvnHome}/bin/mvn test; sleep 3"
            sh "'${mvnHome}/bin/mvn' test surefire-report:report"
              echo "Test done"
      }  
     
      stage('Deploy') {     
            sshagent(['webserver']) {
              // sh 'scp -o StrictHostKeyChecking=no target/tomcatdeploymnetdemo.war saurabh@18.207.247.230:/opt/tomcat/webapps'
                  //cp tomcatdeploymnetdemo.war saurabh@18.212.21.90:/opt/tomcat/webapp
                  //ssh -i ~/.ssh/key.pem -o StrictHostKeyChecking=no saurabh@18.212.21.90 /bin/bash
                // sh 'scp -o StrictHostKeyChecking=no /home/ec2-user/bq saurabh@34.201.126.183:/tmp/'
                 // sh 'scp -o StrictHostKeyChecking=no target/tomcatdeploymnetdemo.war saurabh@18.207.247.230:/tmp/'
                 // sh 'ssh  saurabh@18.207.247.230:"sudo su ; cp /tmp/tomcatdeploymnetdemo.war /opt/tomcat/webapps/" '
                  sh 'scp -o StrictHostKeyChecking=no /home/ec2-user/bq saurabh@34.201.126.183:/tmp/'
                 echo "deployment done "
              
          }
         
     }
      
 }
