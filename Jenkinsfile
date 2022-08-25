node {
    stage("Git Clone"){
        git branch: 'main', credentialsId: 'GIT_HUB_CREDENTIALS', url: 'https://github.com/scott2srikanth1/docker_demo'
    }

    stage("Docker build"){
        sh 'docker version'
        sh 'docker build -t demo_demo .'
        sh 'docker image list'
        sh 'docker tag demo_demo scott2srikanth/demo_demo:latest'
    }

    stage("Push Image to Docker Hub"){
        sh 'docker login -u scott2srikanth -p ******'
        sh 'docker push  scott2srikanth/demo_demo:latest'
    }
}