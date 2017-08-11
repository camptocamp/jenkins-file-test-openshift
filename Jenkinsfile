#!/usr/bin/groovy

// Load shared library
@Library('github.com/camptocamp/c2c-pipeline-library@master') import static com.camptocamp.utils.*

pipeline {
  agent {
    // run with the custom geomapfish slave
    // will dynamically provision a new pod on Openshift
    label 'geomapfish'
  }

  stages {
    stage('test') {
      // TODO
      steps {
        sh returnStdout: true, script: 'pwd'
        sh returnStdout: true, script: 'ls -al'
      }
    }

    stage('deploy-staging') {
      steps {
        sh 'ls'
        // TODO
      }
    }

    stage('deploy-preprod') {
      steps {
        sh 'pwd'
        // TODO
      }
    }

    stage('deploy-prod') {
      steps {
        sh 'pwd'
      }
    }
  }
}