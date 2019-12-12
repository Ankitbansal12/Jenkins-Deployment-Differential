#!groovy
import groovy.json.JsonSlurperClassic
node {
   def gitEXE = env.gitEXE
   def branch = env.BRANCH_NAME
   bat "echo My branch name: ${branch}"
   def commit =env.GIT_COMMIT
   bat "echo My coomit: ${commit}"
   def prevcommit =env.GIT_PREVIOUS_COMMIT
   bat "echo My previous coomit: ${prevcommit}"
    def antVersion = 'Ant'
    jdk = tool name: 'JDK'
    env.JAVA_HOME = "${jdk}"
    
    
	    stage('Checkout code') {
  steps {
    script {
      // Checkout the repository and save the resulting metadata
      def scmVars = checkout([
        $class: 'GitSCM'])

      // Display the variable using scmVars
      echo "scmVars.GIT_COMMIT"
      echo "${scmVars.GIT_COMMIT}"

      // Displaying the variables saving it as environment variable
      env.GIT_COMMIT = scmVars.GIT_COMMIT
      echo "env.GIT_COMMIT"
      echo "${env.GIT_COMMIT}"
    }

    // Here the metadata is available as environment variable
    ...
  }
}
	stage('ANT')
	{
    withEnv( ["ANT_HOME=${tool antVersion}"] ) {
    bat '%ANT_HOME%/bin/ant.bat  builderWithGitDiff'
    }
    
           
    }
	}
