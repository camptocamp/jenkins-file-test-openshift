#!/usr/bin/groovy

// Load shared library
@Library('c2c-pipeline-library') import static com.camptocamp.utils.*

dockerBuild {

    stage 'openshift'

    withEnv(["SKIP_TLS=true"]) {
      openshift.doAs( 'openshift-lab' ) {
        openshiftBuild(
          buildConfig: 'frontend',
          namespace: 'ms-ocpappdev',
          apiURL: 'https://master.dach.openshift.opentlc.com',
          authToken: 'openshift-lab'
        )
      }
    }
}