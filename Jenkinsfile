pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh(script: 'curl -sSfL https://raw.githubusercontent.com/anchore/syft/main/install.sh | \')
	  sh -s -- -b /usr/local/bin v0.54.0
	  chmod +x /usr/local/bin/syft

      }
    }
    stage('Generate SBOM') {
      steps {
        sh 'syft dir:.'
      }
    }
  }
}