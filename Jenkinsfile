
def serviceName = "john_test34"
def buildClosure = { Map args ->
    def version = args.version
    def image = null

    stage('Build') {
        image = docker.build("${serviceName}:${version}")
    }

    return [image]
}

node('docker') {
    cfGitFlowService(
        serviceName: serviceName,
        buildClosure: buildClosure,
        tagOnRelease: false,
        stagingEnvironments: [],
        ciEnvironments: []
    )
}
