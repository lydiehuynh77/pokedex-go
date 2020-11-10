node {
    stage('Checkout Code') {
        checkout scm
    }
    stage('Build image') {
        sh 'docker build -t pokedex-go:latest .'
    }
    stage('Test') {
        sh "docker run --rm pokedex-go:latest npm test"
    }
    stage('Deploy') {
        sh 'docker rm -f mypokedex || true'
        sh 'docker run -d --rm -p 5555:5555 --name mypokedex pokedex-go:latest'
    }
}