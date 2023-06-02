pipeline {
	agent any
	stages {
		stage('build and push image') {
			steps {
				sh '''
				docker build -t gcr.io/lbg-mea-11/sprint3-agray:v1 .
				docker push gcr.io/lbg-mea-11/sprint3-agray:v1
				'''
			}
		}
		stage('cleanup') {
			steps {
				sh 'docker rmi gcr.io/lbg-mea-11/sprint3-agray:v1'
			}
		}
		stage('deploy') {
			steps {
				sh 'kubectl apply -f kubernetes/'
			}
		}
	}
}
