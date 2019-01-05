node {
   def mvnHome
   stage('GitCheckout') { 
      git 'https://github.com/pvnnpavan/calcwebapp'
      mvnHome = tool 'M3'
   }
   stage('MavenCompile') {
      // Run the maven build
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
      } 
   }
   stage('Deploy') {
      sh 'cp target/calcwebapp.war /opt/tomcat/webapps/'
   }
   stage('Email Notification'){
      mail bcc: '', body: '''Pipeline job completed
      Thanks
      Pavan''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'pvnnpavan@live.in'
}
}
