podTemplate(containers: [
        containerTemplate(name: 'maven', image: 'maven:3.6.2-jdk-8-slim', ttyEnabled: true, command: 'cat')
]) {

    node(POD_LABEL) {
        stage('Build a Maven project') {
            git 'https://github.com/neilg/awaitility.git'
            container('maven') {
                sh 'mvn -B clean verify'
            }
        }
    }
}
