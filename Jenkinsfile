pipeline {
  agent any
  stages {
    stage('1-Checkout') { steps { checkout scm } }
    stage('2-Build') { steps { sh 'docker build -t app:${BUILD_NUMBER} .' } }
    stage('3-Push-ECR') { steps { sh 'docker push app:${BUILD_NUMBER}' } }
    stage('4-Deploy-Helm') { steps { sh 'helm upgrade --install app ./helm-chart' } }
    stage('5-Verify') { steps { sh 'kubectl get pods' } }
    stage('6-Monitor') { steps { echo 'Prometheus + Grafana - 4 metrics' } }
    stage('7-Notify') { steps { echo 'Done' } }
  }
}
