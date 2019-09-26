pipeline{
    agent none
    stages {
        stage('Test') {
         agent {
                kubernetes {
                  label 'nodejs-app-inline'
                  yaml """
        kind: Pod
        metadata:
          name: nodejs-app
        spec:
          containers:
          - name: nodejs
            image: node:10.10.0-alpine
            command:
            - cat
            tty: true
          - name: testcafe
            image: 946759952272.dkr.ecr.us-east-1.amazonaws.com/kypseli/testcafe:alpha-1
            command:
            - cat
            tty: true
                  """
                }
              }
        steps {
            container('nodejs'){
             echo 'Hello World!'}
             }
        }
    }
}