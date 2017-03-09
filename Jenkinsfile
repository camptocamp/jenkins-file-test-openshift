#!/usr/bin/groovy

// Load shared library
@Library('c2c-pipeline-library') import static com.camptocamp.utils.*

dockerBuild {

    stage '\u2776 Example Stage 1'
    echo "\u2600 BUILD_URL=${env.BUILD_URL}"
    def workspace = pwd()
    echo "\u2600 workspace=${workspace}"

    stage '\u2777 Print all environment variables'
    sh 'env > env.txt'
    for (String i : readFile('env.txt').split("\r?\n")) {
        println i
    }

    withEnv(["SKIP_TLS=true"]) {
      openshiftBuild(
        buildConfig: 'frontend',
        namespace: 'ms-ocpappdev',
        apiURL: 'https://master.dach.openshift.opentlc.com',
        authToken: 'openshift-lab'
      )
    }
}