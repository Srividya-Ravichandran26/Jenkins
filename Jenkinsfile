pipeline {
  agent any
  stages {
    stage('Dev Build') {
      steps {
        echo 'Git pull code from repo'
      }
    }

    stage('Smoke Test') {
      when {
        branch 'devlopement'
      }
      steps {
        echo 'Print smoke test'
        git(url: 'https://github.com/Srividya-Ravichandran26/EyeAutomation', branch: 'master', poll: true)
        bat(script: 'mvn test -DEnvironment=QA', label: 'QA')
      }
    }

    stage('Cerify') {
      steps {
        echo 'Certify the build!!'
        input(message: 'Are you sure to certify', ok: 'yes')
      }
    }

  }
}