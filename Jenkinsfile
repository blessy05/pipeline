// === Jenkinsfile for 6-stage demo ===

pipeline {
  agent any

  // 4) Environment variables
  environment {
    DIRECTORY_PATH         = '/opt/app/source'
    TESTING_ENVIRONMENT    = 'staging'
    PRODUCTION_ENVIRONMENT = 'Blessy Paul'  // your name as prod env
  }

  stages {

    // 5a) Build
    stage('Build') {
      steps {
        echo 'Fetch the source code from the directory path specified by the environment variable'
        echo "Directory path: ${env.DIRECTORY_PATH}"
        echo 'Compile the code and generate any necessary artefacts'
      }
    }

    // 5b) Test
    stage('Test') {
      steps {
        echo 'Unit tests'
        echo 'Integration tests'
      }
    }

    // 5c) Code Quality Check
    stage('Code Quality Check') {
      steps {
        echo 'Check the quality of the code'
      }
    }

    // 5d) Deploy (to testing env)
    stage('Deploy') {
      steps {
        echo 'Deploy the application to a testing environment specified by the environment variable'
        echo "Testing environment: ${env.TESTING_ENVIRONMENT}"
      }
    }

    // 5e) Approval (pause 10s)
    stage('Approval') {
      steps {
        echo 'Waiting 10 seconds for (simulated) manual approval...'
        sleep time: 10, unit: 'SECONDS'
      }
    }

    // 5f) Deploy to Production
    stage('Deploy to Production') {
      steps {
        echo "Deploying the code to the production environment: ${env.PRODUCTION_ENVIRONMENT}"
      }
    }
  }

  post {
    success { echo 'Pipeline completed successfully ✅' }
    failure { echo 'Pipeline failed ❌' }
  }
}

