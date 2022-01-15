library 'utils@main'
pipeline{
  agent any
  tools
  {maven 'maven'}
  stages{
    stage('lib_from_vars'){
      steps{
        sh 'mvn clean install'
        archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
        echo "completed from jenkins file"
        script{
            paras()
            paras.beta()
            paras.class1()
            //paras.unique('kartik')
        }
      }
    }
  }
}