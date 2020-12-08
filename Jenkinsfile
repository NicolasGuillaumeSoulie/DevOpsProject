pipeline {
    agent any
	

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven: '3_5_0') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven: '3_5_0') {
                    sh 'mvn test'
                }
            }
        }
		

        stage ('Deployment Stage') {
            steps {
                withMaven(maven: '3_5_0', mavenSettingsConfig :"MySettings") {
                    sh 'mvn deploy'
                }
            }
        }
    }
}