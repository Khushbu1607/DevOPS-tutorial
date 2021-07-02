node {
def app

stage('Clone repository')
{
checkout scm
}

stage('Build image')
{
app = docker.build("khushi2/nodeapp")
}

stage('Test image')
{
app.inside {
sh 'echo "Result success"'
}
}

stage('Push image')
{
docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
} 
