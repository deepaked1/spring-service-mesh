node {
   def mvnHome
   def dockerHome
   stage('Preparation') { 
      git 'https://github.com/deepaked1/spring-petclinic.git'
      mvnHome = tool 'M3'
      dockerHome = tool 'Docker'
   }
   stage('Build') {
      withEnv(["DOCKER_HOME=$dockerHome"]) {
	      sh '$DOCKER_HOME/bin/docker version'
      }
      withEnv(["MVN_HOME=$mvnHome"]) {
            sh 'echo $("$MVN_HOME/bin/mvn" -Dmaven.test.failure.ignore -s $MAVEN_SETTINGS clean package)'
      }
   }
}