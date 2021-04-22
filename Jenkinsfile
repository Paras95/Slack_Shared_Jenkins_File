pipeline
{
  agent none

    stages
    {
      stage('Non_Sequential')
      {
          agent any
          steps{
              echo "In Non_Sequential"
          }

      }
      stage('Sequential')
      {
        agent any
        environment
        {
           For_Sequential = 'some_value'

        }

         stages
         {
           stage('In Sequential 1')
           {
               steps{
                echo "In sequential 1"
                sh 'printenv'

               }
           }

           stage('In Sequential 2')
           {
               steps{
                echo "In sequential 2"
                sh 'printenv'

               }
           }

           stage('In Sequential 3')
           {
               steps{
                echo "In sequential 3"

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

                   }
               }

               stage('In Parallel 2')
               {
                   steps{
                      echo 'In parallel 2'

                   }
               }



             }

           }
           
           
        }

      }   



    }



}