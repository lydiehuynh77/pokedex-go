node {
    def app
    stage('Checkout Code') {
        checkout scm
    }
    stage('Build image') {
        app = docker.build('pokedex-go')
    }
    stage('Run image') {
        docker.image('pokedex-go').withRun('-p 5555:5555') { c ->
            sh 'docker ps'
            sh 'curl localhost'
        }
    }
}