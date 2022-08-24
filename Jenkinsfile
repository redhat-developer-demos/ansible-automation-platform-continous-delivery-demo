pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage("Checkout") {
            steps {
                checkout scm
            }
        }
        stage("Docker Build") {
            steps {
               sh '''
                   #oc start-build --from-build=<build_name>
                   oc start-build -F red-api --from-dir=.
               '''
            }
        }
    }
}
