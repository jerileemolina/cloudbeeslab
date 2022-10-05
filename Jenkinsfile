pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        sleep 5
        sh '''echo Success!
'''
        sh '''./jenkins/build.sh
'''
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
      }
    }

    stage('Buzz Test') {
      steps {
        echo 'Placeholder'
        echo 'Another Edited Placeholder'
        sh './jenkins/test-all.sh'
        junit 'target/**/TEST*.xml'
      }
    }

    stage('Fluffy Deploy Stage') {
      steps {
        echo 'Stage 3'
      }
    }

  }
}