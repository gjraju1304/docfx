pipeline {
    agent any
    tools {
        maven 'Maven-3.9.5'
    }
    
    stages {
        stage ('testing') {
            steps {
                git url: 'https://github.com/khajadevopsmarch23/spring-petclinic.git',
                branch: 'main'
                
            }
        }
        stage ('package') {
            steps {
                sh "mvn clean install"
            }
        }
        stage ('artifact') {
            steps {
                archiveArtifacts artifacts: '**/*.jar', followSymlinks: false
            }
        }
        stage ('unit-test') {
            steps {
                junit '**/TEST*.xml'
            }
        }
    }
}
