node {
	  stage('SCM Checkout') {		
		  echo 'checkout stage started'
		  git 'https://github.com/edureka27/maven'
		  echo 'checkout stage completed'			
	  }
	  stage('Compile Stage') {		
		  echo 'compile stage started'
		  def MAVEN_HOME = tool name: 'Maven', type: 'maven'
		  bat "${MAVEN_HOME}/bin/mvn clean compile"
		  echo 'compile stage completed'			
	  }
	  stage('Test Stage') {		
		  echo 'test stage started'
		  def MAVEN_HOME = tool name: 'Maven', type: 'maven'
		  bat "${MAVEN_HOME}/bin/mvn test"
		  echo 'test stage completed'			
	  }
}
