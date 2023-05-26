pipeline {

	agent any
	stages {
		stage('pre-build clean') {
			steps {
				sh 'docker system prune -f'
			}
		}
		stage('build containers') {
			steps {
				sh '''
				docker network create lbg-net
				docker build -t lbg .
				docker run -d --network lbg-net --name lbg lbg
				docker run -d --network lbg-net --name nginx --mount type=bind,source=$(pwd)/nginx.conf,target=/etc/nginx/nginx.conf -p 80:80 nginx:alpine
				'''
			}
		}
	}
}
