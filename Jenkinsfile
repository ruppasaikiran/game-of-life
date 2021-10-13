pipeline {
    agent any
    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "Maven_runtime"
    }
    stages {
        stage ('Compile Stage') {

            steps {
                    git 'https://github.com/ruppasaikiran/game-of-life.git'
                    sh 'mvn clean compile'
                }
            }

        stage ('Testing Stage') {

            steps {
                git 'https://github.com/ruppasaikiran/game-of-life.git'
                    sh 'mvn test'
                }
            }
                    


        stage ('Package Stage') {
            steps {
                git 'https://github.com/ruppasaikiran/game-of-life.git'
                    sh 'mvn package'
                }
            }
     stage ('deployment') {
            steps {
                //git 'https://github.com/ruppasaikiran/game-of-life.git'
                    sh 'scp /var/lib/jenkins/workspace/pipeline/gameoflife-web/target/gameoflife.war root@172.31.47.158:/opt/tomcat/apache-tomcat-8.5.72/webapps'
                }
            }
        }
    }
