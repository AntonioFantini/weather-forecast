pipeline {
  agent any
  stages {
    stage('') {
      steps {
        git(url: 'https://github.com/AntonioFantini/gates-tool.git', branch: 'master')
        load 'license-checks/LicenseChecks.groovy'
      }
    }
  }
}