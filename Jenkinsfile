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

                    deploy adapters: [tomcat7(credentialsId: '123', path: '', url: 'http://localhost:8090/manager/html')], contextPath: 'gameoflife-build-1.0-SNAPSHOT', war: '**/*.war'
                    bat label: '', script: 'mvn deploy'
                }

            }

    }

}
