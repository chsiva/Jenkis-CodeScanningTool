pipeline {
    agent any


    parameters {
        string(defaultValue: 'admin', description: 'provide Jfrog Username', name: 'USERNAME')
        password(defaultValue: 'abc*12', description: 'provide Jfrog Password', name: 'PASSWORD')
    }



    stages {
        stage('ArtifactUpload') {
            steps {
              sh '''
              cp /opt/artifactory.tar.gz ${WORKSPACE}/
              curl -u ${USERNAME}:${PASSWORD} -T ${WORKSPACE}/artifactory.tar.gz "http://localhost:8081/artifactory/test/"
              '''
            }
        }
         stage('ArtifactDownload') {
            steps {
              sh '''
              curl -u ${USERNAME}:${PASSWORD} "http://localhost:8081/artifactory/test/artifactory.tar.gz"  -O /tmp/artifactory.tar.gz
              '''
            }
        }
    }
}
