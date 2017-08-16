pipeline {
  agent any
  stages {
    stage('LicenseChecks') {
      steps {
        git(url: 'https://github.com/AntonioFantini/gates-tool.git', branch: 'master')
        load 'licenses-checks/LicensesChecks.groovy'
      }
    }
    stage('CryptoChecks') {
      steps {
        load 'crypto-checks/CryptoChecks.groovy'
      }
    }
    stage('DependenciesChecks') {
      steps {
        load 'dependencies-checks/DependenciesChecks.groovy'
      }
    }
  }
}