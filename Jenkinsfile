pipeline {
  agent any
  stages {
    stage('Licenses Checks') {
      steps {
        git(url: 'http://git.app.eng.bos.redhat.com/git/jboss-prod-core/gates.git/', branch: 'master')
        load 'gates/licenses/RunGate.groovy'
        script {
          currentBuild.displayName = "release"
          currentBuild.description = "release desc"
        }
        
      }
    }
    stage('Crypto Checks') {
      steps {
        load 'gates/crypto/RunGate.groovy'
      }
    }
    stage('CVEs Checks') {
      steps {
        load 'gates/cves/RunGate.groovy'
      }
    }
    stage('SourceCodeLocation Checks') {
      steps {
        load 'gates/sourcecodelocation/RunGate.groovy'
      }
    }
    stage('Dependencies Checks') {
      steps {
        load 'gates/dependencies/RunGate.groovy'
      }
    }
  }
}