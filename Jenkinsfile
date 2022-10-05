pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        sleep 5
        sh 'echo "I am a ${BUZZ_NAME}"'
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
        sh './jenkins/build.sh'
      }
    }

    stage('Buzz Test') {
      parallel {
        stage('Buzz Test') {
          steps {
            echo 'Placeholder'
            echo 'Another Edited Placeholder'
            sh './jenkins/test-all.sh'
            junit '**/surefire-reports/**/*.xml'
          }
        }

        stage('Prueba B') {
          steps {
            echo 'Prueba paralela'
            sh '''sleep 10
echo done'''
          }
        }

      }
    }

    stage('Fluffy Deploy Stage') {
      steps {
        echo 'Stage 3'
      }
    }

  }
  environment {
    BUZZ_NAME = 'Worker Bee'
  }
}