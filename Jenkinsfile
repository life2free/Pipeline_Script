pipeline{
    agent none
    stages {
        stage('Non-parallel Stage') {
		    agent{
		        label 'master'
		    }
            steps{
                echo 'This stage will be excuted first' 
            }
        }
        stage('Run Tests') {
            parallel{
                stage('Run Test on Windows'){
                    agent{
                        label 'WindowsNode'
                    }
                    steps{
                        echo 'Task on Agent'
                    }
                }
                stage('Run Test on Master'){
                    agent{
                        label 'master'
                    }
                    steps{
                        echo 'Task on Master'  
                    }
                }
            }
        }
    }
}
