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
            paras.class1('target/surefire-reports/TEST-com.mycompany.app.AppTest.xml')
            //paras.unique('kartik')
        }
      }
    }
  }
}