﻿

}
pipeline { agent {
docker {
image 'node: 14'
}
}
stages {
stage('Clone repository') {
steps {
}
}
git branch: 'main',
url: 'https://github.com/<user>/<repo>.git'
stage('Install dependencies') {
steps {
sh 'npm install'
}
}
stage('Build application') { steps {
sh 'npm run build'
}
}
stage('Test application') { steps {
sh 'npm test'
}
}
stage('Push Docker image') {
steps {
sh 'docker build -t <user>/<image>: $BUILD_NUMBER .' sh 'docker push <user>/<image>: $BUILD_NUMBER'
}
}
}
