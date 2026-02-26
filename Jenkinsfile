stage('Deploy NGINX Load Balancer') {
    steps {
        sh '''
        docker rm -f nginx-lb || true

        docker run -d \
          --name nginx-lb \
          --network app-network \
          -p 80:80 \
          -v $(pwd)/nginx/default.conf:/etc/nginx/conf.d/default.conf \
          nginx
        '''
    }
}
