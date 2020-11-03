node {
    stage('Checkout Code') {
        checkout scm
    }
    stage('Build image') {
        sh 'docker build -t pokedex-go .'
    }
    stage('Run image') {
        sh 'docker run --rm -it -p 5555:5555 pokedex-go:latest'
    }
}