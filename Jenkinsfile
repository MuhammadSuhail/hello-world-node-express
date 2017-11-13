
node('') {
stage 'testInDevelopment'
checkout scm
sh '''ls -lhrt'''
def rootDir = pwd()
println("Current Directory: " + rootDir)
def example = load "${rootDir}/externalMethod.groovy"
example.exampleMethod()
stage 'buildInDevelopment'
openshiftBuild( buildConfig: 'nodejs-mongodb-example', showBuildLogs: 'true')
stage 'deployInDevelopment'
openshiftDeploy( deploymentConfig: 'nodejs-mongodb-example')

}
