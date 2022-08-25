node {
    stage("Git Clone"){
        git branch: 'main', credentialsId: 'GIT_HUB_CREDENTIALS', url: 'https://github.com/scott2srikanth1/docker_demo'
    }

    stage("Docker build"){
        sh 'docker version'
        sh 'docker build -t mydemo .'
        sh 'docker image list'
        sh 'docker tag mydemo scott2srikanth/mydemo:latest'
    }
    

    stage("Push Image to Docker Hub"){
        withCredentials([string(credentialsId: 'dockerhub', variable: 'password')]) {
            sh 'docker login -u scott2srikanth -p '${password}
        }
        sh 'docker push  scott2srikanth/mydemo:latest'
    }
}