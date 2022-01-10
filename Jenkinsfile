pipeline
{
  agent {label 'docker-agent-slave' }

  /*triggers {
        pollSCM('* * * * *')
    }*/

  options
  {
    buildDiscarder(logRotator(numToKeepStr: '4')) 
  }

  parameters
  {

      string(name: 'PERSON', defaultValue: 'Jenkins', description: 'Who should i say hello to')
      text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

      booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

      choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

      password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
  }
   environment
        {
           For_Sequential = 'some_value'
           My_Password = credentials('6ad7401e-6579-4543-b948-ff2bd52cb366')

        }
      tools
      {
      maven 'maven'
      }

    stages
    {

      stage('Non_Sequential')
      {
        when { environment name: 'For_Sequential', value: 'some_value' }

          input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
          }
          
          agent any
          steps{
               sh 'mvn clean install'
              echo "In Non_Sequential"
              echo "My Name is ${params.PERSON}"
              
          }

      }
      stage('Sequential')
      {
        agent any
        environment
        {
           For_Sequential = 'some_value'
           My_Password = credentials('6ad7401e-6579-4543-b948-ff2bd52cb366')

        }

         stages
         {
           stage('In Sequential 1')
           {
               steps{
                echo "In sequential 1"
                sh 'printenv'
                echo "In sequential 1 ${params.PERSON}"

               }
           }

           stage('In Sequential 2')
           {
               steps{
                echo "In sequential 2"
                sh 'printenv'
                echo "In sequential 2 ${params.PERSON}"

               }
           }

           stage('In Sequential 3')
           {
               steps{
                echo "In sequential 3"
                echo "In sequential 3 ${params.PERSON}"

               }
           }
           stage('Parallel in sequential')
           {

             parallel
             {

               stage('In Parallel 1')
               {
                   steps{
                      echo 'In parallel 1'
                      echo "In parallel 1 ${params.PERSON}"

                   }
               }

               stage('In Parallel 2')
               {
                   steps{
                      echo 'In parallel 2'
                      echo "In parallel 2 ${params.PERSON}"

                   }
               }



             }

           }
           
           
        }

      }   



    }



}
