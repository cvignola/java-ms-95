#!groovy

node('master') {

  def utils = load "/scripts/buildUtils.groovy"

  stage ('Extract') {
    checkout scm
  }

  stage ('Build') {
    utils.mavenBuild ('clean', 'package')
    utils.dockerBuild('javams95')
  }

  stage ('Deploy') {
    utils.deploy ()
  }
}
