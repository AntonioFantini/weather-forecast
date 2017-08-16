pipeline {
  agent any
  stages {
    stage('LicenseChecks') {
      steps {
        git(url: 'https://github.com/AntonioFantini/gates-tool.git', branch: 'master')
        load 'licenses/RunGate.groovy'
      }
    }
    stage('CryptoChecks') {
      steps {
        load 'crypto/RunGate.groovy'
      }
    }
    stage('DependenciesChecks') {
      steps {
        load 'dependencies/RunGate.groovy'
      }
    }
    stage('CVEsChecks') {
      steps {
        load 'cves/RunGate.groovy'
      }
    }
    stage('SourceCodeLocationChecks') {
      steps {
        load 'sourcecodelocation/RunGate.groovy'
      }
    }
  }
}