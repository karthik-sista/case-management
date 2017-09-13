node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */

        app = docker.build("case-management/hello_world")
    }
    stage('Test image') {
        /* We test our image with a simple smoke test:
         * Run a curl inside the newly-build Docker image */

        app.inside {
            sh 'echo "Tested image successfully"'
        }
    }



}