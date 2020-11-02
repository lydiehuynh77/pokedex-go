node {
    stage('Checkout Code') {
        checkout scm
    }
    def img = stage('Build image') {
        docker.build('pokedex-go:version-${env.BUILD_ID}', .)
    }
    stage('Run container from image') {
        img.withRun('--name run-$BUILD_ID -p 5555:5555')
    }
}