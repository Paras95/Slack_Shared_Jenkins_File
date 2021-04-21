pipeline{
  
  agent any

  tools
  {
    maven 'maven'

  }
    stages
    {
        stage('Build')
        {
            steps
            {
             echo "kartik beta mera hai"
             sh "mvn clean"
             sh "mvn package"            
            }
        }
    }
    post {
        always {
            junit '**/*.xml'
        }
    }

}