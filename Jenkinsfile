pipeline{
    agent{
        node(label: 'node')
    }

    tools{
        maven 'MVN'
        jdk   'Java_17'
    }

    stages{
        stage(CLEANWS){
            steps{
                cleanWs()
            }
            
        }
        stage(GIT){
            steps{
                git branch: 'main', url: 'https://github.com/RukhsanaBegm/spring-petclinic'
            }
        }

        stage(build) {
            steps{
                sh(script: 'mvn package')
            }
            

        }
        stage(archiveArtifacts) {
            steps{
                archiveArtifacts(artifacts: '**/*.jar')
            }
            
        }

    }


}