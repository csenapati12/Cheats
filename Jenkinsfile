node {
    checkout scm

    docker.withRegistry('https://registry.hub.docker.com/', 'dockerHub') {

        def customImage = docker.build("testapp:${env.BUILD_ID}")

        /* Push the container to the custom Registry */
        sh "docker tag testapp:${env.BUILD_ID} cheplorna/lorna:testapp"
        sh "docker login"
        sh "docker push cheplorna/lorna:testapp"
    }
}
