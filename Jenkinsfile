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
deploy adapters: [tomcat8(credentialsId: '85d1be26-0496-4c24-b958-d3e5a6c3713a', path: '', url: 'http://44.199.227.184:8080')], contextPath: null, war: '**/*.war'        }
    }
  }
}
