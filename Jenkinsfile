node {
    stage('Checkout_repo') {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/samsonawane/docker_sample.git']]])
    }
    stage ('build')
    {
        withCredentials([usernamePassword(credentialsId: 'docker_login', passwordVariable: 'docker_password', usernameVariable: 'docker_id')]) {
    // some block
    }
        sh '''echo "Docker user id - "${docker_id}
        echo "docker password-" ${docker_password}
        
        docker login -u ${docker_id} -p ${docker_password}
        
        docker build -t 146710/sam_build:dindsample_${BUILD_NUMBER} .
        
        docker push 146710/sam_build:dindsample_${BUILD_NUMBER}'''
    }
}
