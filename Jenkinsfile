pipeline
{
  agent none

    stages
    {
      stage('Non_Sequential')
      {
          agent{
              label 'For Non_Sequential'
          }
          steps{
              echo "In Non_Sequential"
          }

      }
      stage('Sequential')
      {
        agent{
         label 'For Sequential'

        }
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

               }
           }

           stage('In Sequential 2')
           {
               steps{
                echo "In sequential 2"

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

               stage
               {
                   steps{
                      echo 'In parallel 1'

                   }
               }

               stage
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