node {
   def mvnHome
   stage('GitCheckout') { 
      git 'https://github.com/pvnnpavan/calcwebapp'
      mvnHome = tool 'M3'
   }
   stage('MavenCompile') {
      // Run the maven build
      bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      } 

   stage('Deploy') {
      //copy target/calcwebapp.war "C:/Program Files/Apache Software Foundation/Tomcat 8.5/webapps"
            String sourceFilePath = "C:/Program Files (x86)/Jenkins/workspace/Projectcode/target/calcwebapp.war"
            String destinationFilePath = "C:/Program Files/Apache Software Foundation/Tomcat 8.5/webapps/calcwebapp.war"
            (new AntBuilder()).copy(file: sourceFilePath, tofile: destinationFilePath)
      }
   
   stage('Email Notification'){
      mail bcc: '', body: '''Pipeline job completed
      Thanks
      Pavan''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'pvnnpavan@live.in'
}
}


node {
   def mvnHome
   stage('GitCheckout') { 
      git 'https://github.com/pvnnpavan/calcwebapp'
      mvnHome = tool 'M3'
   }
   stage('MavenCompile') {
      // Run the maven build
      bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      } 
   
   stage('Deploy') {
      //copy target/calcwebapp.war "C:/Program Files/Apache Software Foundation/Tomcat 8.5/webapps"
            String sourceFilePath = "C:/Program Files (x86)/Jenkins/workspace/Projectcode/target/calcwebapp.war"
            String destinationFilePath = "C:/Program Files/Apache Software Foundation/Tomcat 8.5/webapps/calcwebapp.war"
            (new AntBuilder()).copy(file: sourceFilePath, tofile: destinationFilePath)
      }
}
