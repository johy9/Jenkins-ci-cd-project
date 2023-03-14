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
deploy adapters: [tomcat9(credentialsId: 'c5523984-9bdd-46f5-8be2-c6af844d1a2a', path: '', url: 'http://44.202.214.147:8080/')], contextPath: null, onFailure: false, war: '**/*.war'     }
  }
}
