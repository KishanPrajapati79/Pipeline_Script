pipeline {
    agent none
    stages {
	
	stage('Non-Parallel Stage') {
        	steps {
                	echo 'This stage will be executed first'
                }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On agent') {
                    agent {
                        label "agent1"
                    }
                    steps {
                        echo "Task1 on Agent"
                    }
                    
                }
                stage('Test On Master') {
                    steps {
						echo "Task1 on Built-In-Node"
					}
                }
            }
        }
    }
}
