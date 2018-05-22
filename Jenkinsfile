node {
  stage 'build'
  docker.image('kohsuke/acmecorp-buildenv').inside {
    git 'https://github.com/birla01/docker-jenkins-demo-app.git'
    sh 'mvn install'
    archive 'target/*.war'
  }

  stage 'package'
  docker.build('kohsuke/acmecorp-app').push()
      echo "stage passed"
  stage 'deploy'
  sh './deploy.sh'
}
