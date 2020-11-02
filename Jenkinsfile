node {
    stage('Checkout Code') {
        checkout scm
    }
    def img = stage('Build image') {
        docker.build('-t pokedex-go .')
    }
    stage('Run container from image') {
        img.withRun('run --rm -it -p 5555:5555 pokedex-go:latest')
    }
}