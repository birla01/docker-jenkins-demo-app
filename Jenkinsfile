node {
  stage 'build'
  docker.image('kohsuke/acmecorp-buildenv').inside {
    git 'https://github.com/birla01/docker-jenkins-demo-app.git'
    sh 'mvn install'
    archive 'target/*.war'
  }

  stage 'package'
  docker.build('birla01/acmecorp-app').push()

  stage 'deploy'
  sh './deploy.sh'
}
