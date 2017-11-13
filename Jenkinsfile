node('') {

stage 'buildInDevelopment'
checkout scm
sh '''ls -lhrt'''
openshiftBuild( buildConfig: 'nodejs-mongodb-example', showBuildLogs: 'true')
stage 'deployInDevelopment'
openshiftDeploy( deploymentConfig: 'nodejs-mongodb-example')

}
