pipeline{
  
  agent any

  tools
  {
    maven 'Maven 3.6.3'

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

}