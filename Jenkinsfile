pipeline{
    agent any
    tools{
        maven 'local_maven'
    }
     stages {
            stage('build') {
                steps {
                    echo 'Building..'
            sh '/usr/share/maven/bin/mvn clean package'
                }
            }
            stage('test') {
                steps {
                    echo 'Building..'
            sh '/usr/share/maven/bin/mvn test'
                }
            }
            stage('deploy') {
                steps {
                    echo "Deploying...."
deploy adapters: [tomcat8(credentialsId: 'a661ed1f-6861-4471-ba55-65f973900239', path: '', url: 'http://44.199.227.184:8080')], contextPath: null, war: '**/*.war'    }
     }
  }
}
