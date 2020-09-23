#!/usr/bin/env groovy
@Library('shared-library@master') _ //master or whatever branch
deploying([
  adapter:[tomcat8(credentialsId: '5866d9c5-7497-4a2f-9477-39037e355cb6', path: '', url:'http://localhost:8083/')],
  context: "myproject",
  warr: "**/*.war"
])
