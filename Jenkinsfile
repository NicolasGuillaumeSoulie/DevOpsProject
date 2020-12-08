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
                withMaven(maven: '3_5_0', mavenSettingsConfig :"031fb25a-ad1a-4184-a4ec-624d65d6ee6c") {
                    sh 'mvn deploy'
                }
            }
        }
    }
}