pipeline {
    agent none
    stages {
	
	stage('Non-Parallel Stage') {
	    agent {
                        label "Built-In-Node"
                }
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
                    agent {
                        label "Built-In-Node"
                    }
                    steps {
						echo "Task1 on Built-In-Node"
					}
                }
            }
        }
    }
}
