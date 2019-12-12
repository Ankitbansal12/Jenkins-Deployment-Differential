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
    
    stage('checkout source') {
        // when running in multi-branch job, one must issue this command
        checkout scm
    }
	stage('ANT')
	{
    withEnv( ["ANT_HOME=${tool antVersion}"] ) {
    bat '%ANT_HOME%/bin/ant.bat  builderWithGitDiff'
    }
    
           
    }
	}
