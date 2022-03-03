#!/bin/env groovy

// Sandbox Account
def target_bucket = 'totallynottheinternprojectpartone.com' // your s3 bucket name to deploy to
def region  = 'us-east-2'

// pipeline manifest job
def partOneSRE7OperationalManifestPath = ''

//build information
def revision = '0.0.0'
def build_number = env.BUILD_ID
def allowSnapshots = ''
def parent_updater = 'versions:update-parent'


pipeline {
    agent {
        docker { image 'golang:1.14-alpine'
                 args '-u 0'
               }
    }
    parameters {
        booleanParam(name: 'DOWNSTREAM_TRIGGER', defaultValue: false, description: 'Parameter to control BuiltBlockerProperty if started by upstream')
    }
    environment {
        HOME = '.'
    }
    options {
        ansiColor('xterm')
        timestamps()
        disableConcurrentBuilds()
        buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
    }
    stages {
        stage('Publish') {
            steps {
                echo '''\
                    *****************************************************************
                    ************************ PUBLISH TO Non Prd S3 ******************
                    *****************************************************************
                '''.stripIndent()

                withCredentials([[ $class: 'AmazonWebServicesCredentialsBinding',
                                   credentialsId: 'jenkins-aws-asmt-sre-sandbox-125616717413',
                                 ]]){
                                     
                    sh "apk add zip"
                    sh "apk add --no-cache curl jq python3 py3-pip"
                    sh "pip3 install awscli"

                    sh "aws --version"
                    
                    sh "aws s3 cp Project-One/upload s3://totallynottheinternprojectpart1.com --recursive --acl public-read"

                }
            }
        }
    }
}
//         stage('Trigger RC Job') {
//             steps {
//                 milestone(ordinal: 2, label: "Trigger Manifest Job")
//                 echo '''\
//                     *****************************************************************
//                     *********************** TRIGGER PIPELINE ************************
//                     *****************************************************************
//                 '''.stripIndent()
//
//                 build job: maydaySRE7OperationalManifestPath,
//                 parameters: [
//                     string(name: 'MANIFEST_TYPE', value: "backend"),
//                     string(name: 'MANIFEST_KEY', value: "pagerduty-pager-lambda"),
//                     string(name: 'MANIFEST_VALUE', value: "build-${build_number}.zip"),
//                 ],
//                 wait: false
//             }
//         }
    // post {
    //     failure {
    //         emailext (
    //             to: "team7-sre@pearson.com ",
    //             subject: "The jenkins job failed: '${currentBuild.fullDisplayName}'",
    //             body: "See the output for more details: ${env.BUILD_URL}"
    //         )

    //         slackSend(  channel: "#og-rocks" ,
    //                     message: "The ${currentBuild.fullDisplayName} job failed!\n\nSee the output for more details: $BUILD_URL",
    //                     color: "danger",
    //                     tokenCredentialId: "AIDEVOPS_SLACK_INTEGRATION_TOKEN")
    //     }
    //     changed {
    //          script {
    //             if (currentBuild.currentResult == 'SUCCESS') {
    //                 emailext (
    //                     to: "cde-team1@pearson.com ",
    //                     subject: "The jenkins job '${currentBuild.fullDisplayName}' is back to normal",
    //                     body: "See the output for more details: ${env.BUILD_URL}"
    //                 )

    //                 slackSend(
    //                     channel: "#og-rocks",
    //                     message: "The ${currentBuild.fullDisplayName} job succeeded!\n\nSee the output for more details: $BUILD_URL",
    //                     color: "good", tokenCredentialId: "AIDEVOPS_SLACK_INTEGRATION_TOKEN")
    //             }
    //         }
    //     }
    // }

