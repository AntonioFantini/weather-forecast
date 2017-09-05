pipeline {
  agent any
  stages {
    stage('LicenseChecks') {
      steps {
        git(url: 'https://github.com/AntonioFantini/gates-tool.git', branch: 'master')
        load 'licenses/RunGate.groovy'
        script {
          currentBuild.displayName = "release"
          currentBuild.description = "release desc"
        }
        
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
    stage('CommunityArtifactsVersioningChecks') {
      steps {
        load 'communityartifactsversioning/RunGate.groovy'
      }
    }
  }
}