#!groovy

node('master') {
    stage('Checkout') {
        checkout scm
        echo 'Repository checked out'
    }

    stage('Run Zalenium'){
        sh 'sudo docker run --rm -ti --name zalenium -p 4444:4444 \
            -v /var/run/docker.sock:/var/run/docker.sock \
            -v /tmp/videos:/home/seluser/videos \
            --privileged dosel/zalenium start'
        echo 'Zalenium running'
    }
}
