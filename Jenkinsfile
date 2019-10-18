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

                    deploy adapters: [tomcat7(credentialsId: 'b971d196-c2b6-47f3-b060-1c7fdf2db6ec', path: '', url: 'http://localhost:8090/manager/html')], contextPath: null, war: '**/*.war'

                }

            }

    }

}
