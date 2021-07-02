node {
def app

stage('Clone repository')
{
checkout scm
}

stage('Build image')
{
app = docker.build("Khushbu1607/Khushbu")
}

stage('Test image')
{
app.inside {
sh 'echo "Result success"'
}
}

stage('Push image')
{
docker.withRegistry('https://registry.hub.docker.com', 'docker-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
} 
