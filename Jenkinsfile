pipeline {
  agent any
  stages {
    stage('LicenseChecks') {
      steps {
        git(url: 'https://github.com/AntonioFantini/gates-tool.git', branch: 'master')
        load 'license-checks/LicenseChecks.groovy'
      }
    }
    stage('CryptoChecks') {
      steps {
        load 'crypto-checks/CryptoChecks.groovy'
      }
    }
  }
}