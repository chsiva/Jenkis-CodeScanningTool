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
              curl -u ${USERNAME}:${PASSWORD} -T ${WORKSPACE} "http://104.197.247.41:8081/artifactory/test/"
              '''
            }
        }
    }
}
