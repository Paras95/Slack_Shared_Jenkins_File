library 'utils'
pipeline{
  agent any
  tools
  {maven 'maven'}
  stages{
    stage('lib_from_vars'){
      steps{
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