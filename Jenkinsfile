#!groovy
import groovy.json.JsonSlurperClassic
node {
  
    def antVersion = 'Ant'
    jdk = tool name: 'JDK'
    env.JAVA_HOME = "${jdk}"
    
        stage('Checkout') {
             
	   checkout([$class: ‘GitSCM’, branches: [[name: ‘/feature/’]], doGenerateSubmoduleConfigurations: false, extensions: [[$class: ‘LocalBranch’, localBranch: “**”]], submoduleCfg: [], userRemoteConfigs: [[credentialsId: ‘04f62bdf-e233-XXXX-XXXX-4fd5df294637’, url: ‘ssh://geek-kb@geek-kb.visualstudio.com:22/_git/scripts’]]])
                          }
	stage('ANT')
	{
    withEnv( ["ANT_HOME=${tool antVersion}"] ) {
    bat '%ANT_HOME%/bin/ant.bat  builderWithGitDiff'
        }
    
           
    }
	}
