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
deploy adapters: [tomcat8(credentialsId: 'd0408b5d-ddf2-407a-b9fb-c3b1504bacd3', path: '', url: 'http://34.201.15.106:8080')], contextPath: null, war: '**/*.war'            }
        }
    }
}
