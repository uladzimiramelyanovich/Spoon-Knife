node('master') {
  stage('SCM') {
    checkout poll: false, scm: [$class: 'GitSCM', branches: [[name: 'refs/heads/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/uladzimiramelyanovich/Spoon-Knife.git']]]
  }
  stage ('Groovy samples') {
	x = 1
	println x
	x = new java.util.Date()
	println x
	x = -3.1499392
	println x
	x = false
	println x
	x = "Hi"
	println x
  }
  stage('SonarQube Analysis') {

  sh "/var/jenkins_home/tools/sonar-scanner-3.3.0.1492-linux/bin/sonar-scanner -Dsonar.host.url=http://172.19.0.2:9000 -Dsonar.projectName=Spoon-Knife -Dsonar.projectVersion=1.0 -Dsonar.projectKey=spoon-knife:app -Dsonar.sources=. -Dsonar.projectBaseDir=/var/jenkins_home/workspace/"
    }
  }
