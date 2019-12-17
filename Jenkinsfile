#!groovy
import groovy.json.JsonSlurperClassic
node {
  
    def antVersion = 'Ant'
    jdk = tool name: 'JDK'
    env.JAVA_HOME = "${jdk}"
    
    
	    stage('Checkout') {
             
		    checkout scm
}
	stage('ANT')
	{
    withEnv( ["ANT_HOME=${tool antVersion}"] ) {
    sh '%ANT_HOME%/bin/ant.bat  builderWithGitDiff'
    }
    
           
    }
	}
