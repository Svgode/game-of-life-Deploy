pipeline {
agent {
label {
		label "built-in"
		customWorkspace "/data/project-myapp"
		
		}
		}
		
	stages {
		
		stage ('CLEAN_OLD_M2') {
			
			steps {
				sh "rm -rf /home/ec2-user/.m2/repository"
				
			}
			
		}
	
		stage ('MAVEN_BUILD') {
		
			steps {
						
						sh "mvn clean package"
			
			}
			
		
		}
		
		stage ('COPY_WAR_TO_Server'){
		
				steps {
						
						sh "sudo scp -i /root/test.pem /data/project-myapp/gameoflife-web/target/gameoflife.war ec2-user@10.0.2.51:/data/project-myapp/wars"

						}
				
				}
	
	
	
	}
		
}
