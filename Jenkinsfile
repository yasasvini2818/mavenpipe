pipeline
{
   agent any
   tools{
      maven 'Maven'
   }
   stages
   {
     stage('Checkout')
     {
       steps
       {
         git branch:'master',url:'https://github.com/yasasvini2818/mavenpipe.git'
       }
     }
     stage('Build')
     {
       steps
       {
         sh'mvn clean package'
       }
     }
     stage('Test')
     {
       steps
       {
         sh'mvn test'
       }
     }
     stage('Run Application')
     {
       steps
       {
         sh'java -jar target/mavenpipeline-1.0-SNAPSHOT.jar'
       }
     }
  }
  post
  {
    success
    {
       echo Build and run successful
    }
    failure
    {
       echo Build failed
    }
 }
}
