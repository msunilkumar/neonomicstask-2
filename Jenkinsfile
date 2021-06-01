pipeline{
    agent { label 'neo-k8s' }
    
    stages{
        stage('SCM'){
            steps{
                git credentialsId: 'github', url: 'https://github.com/msunilkumar/neonomicstask-2.git'
            }
        }
        stage('Docker compose'){
            steps{
                step([$class: 'DockerComposeBuilder', dockerComposeFile: 'docker-compose.yml', option: [$class: 'StartAllServices'], useCustomDockerComposeFile: true])
            }
        }
        
    }
}
