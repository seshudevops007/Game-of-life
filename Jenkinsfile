pipeline {

    agent any



    stages {

        stage ('Compile Stage') {



            steps 

              {

                   bat label: '', script: 'mvn compile'

                }

            }

        
        stage ('Testing Stage') {



            steps 

                 {

                    bat label: '', script: 'mvn test'

                }

            

        }





        stage ('Package Stage') {

            steps 

                {

                    bat label: '', script: 'mvn package'

                }

            }

        stage ('Deploy Stage') {

            steps 

                {

                    deploy adapters: [tomcat7(credentialsId: '7b122523-fe25-48eb-b7ed-746a0f36a14b', path: '', url: 'http://localhost:8090/manager/html')], contextPath: null, war: '**/*.war'
                    bat label: '', script: 'mvn compile'
                }

            }

    }

}
