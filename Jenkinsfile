pipeline{

    agent any
    tools {
        maven 'Apache Maven 3.6.3'
        jdk 'JDK8'
    }
    stages {

        stage ('Compile Stage') {

            steps {

                script {
                    sh 'mvn clean install'

                }

            }
        }
    stage ('Test Stage') {

            steps {

                script {
                    sh 'mvn test'

                }

            }
        }


        stage ('Cucumber Reports') {

            steps {
                cucumber buildStatus: "UNSTABLE",
                    fileIncludePattern: "**/cucumber.json",
                    jsonReportDirectory: 'target'

            }

        }

    }

}
