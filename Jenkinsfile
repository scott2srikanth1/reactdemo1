node {
    stage("Git Clone"){
        git branch: 'main', credentialsId: 'GIT_HUB_CREDENTIALS', url: 'https://github.com/scott2srikanth1/reactdemo1'
    }

    stage("Docker build"){
        sh 'docker version'
        sh 'docker build -t mydemo .'
        sh 'docker image list'
        sh 'docker tag mydemo scott2srikanth/mydemo:latest'
    }


    withCredentials([string(credentialsId: 'abc', variable: 'password')]) {
        sh 'docker login -u scott2srikanth -p $password'
    }
    

    stage("Push Image to Docker Hub"){
        sh 'docker push  scott2srikanth/mydemo:latest'
    }
}