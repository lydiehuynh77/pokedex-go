node {
    stage('Checkout Code') {
        checkout scm
    }
    stage('Build image') {
        docker build -t pokedex-go .
    }
    stage('Run container from image') {
        docker run --rm -it -p 5555:5555 pokedex-go:latest
    }
}
