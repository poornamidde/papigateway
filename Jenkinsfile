node {
stage("Git Clone"){

git branch: 'main', url: 'https://github.com/chanakyad/APIgateway.git'
}
stage ("Maven clean&install")
  {
    sh "mvn clean"
    sh "mvn install"
    sh "ls"
  }
stage("Docker build"){
sh 'docker build -t apigateway .'
sh 'docker images'
stage("Deploy"){
sh 'docker rm -f apigateway||true'
sh ' docker run -itd -p 9090:9090 --name apigateway apigateway'
}
}
}
