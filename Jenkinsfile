pipeline{
    agent any
    stages{
        stage("SCM"){
            steps{
                git branch: 'master', url: 'https://github.com/sduggi/sonarqube_python.git'
            }
        }
        stage("test in Sonarqube"){
            steps{
                sh "nosetests -sv --with-xunit --xunit-file=nosetests.xml --with-xcoverage --xcoverage-file=coverage.xml"
                withSonarQubeEnv(installationName: 'sonarqube-server', credentialsId: 'sonarqube-credentials') {
                    sh "${ tool ("sonar-scanner")}/sonar-scanner \
                        -Dproject.settings=sonar-scanner.properties"
                }
            }
        }
    }
}
