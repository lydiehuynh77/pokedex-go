node {
    stage('Checkout Code') {
        checkout scm
    }
    stage('Build image') {
        sh 'docker build -t pokedex-go .'
    }
    stage('Run image') {
        sh 'docker rm -f mypokedex || true'
        sh 'docker run -d --rm -p 5555:5555 --name mypokedex pokedex-go:latest'
    }
}