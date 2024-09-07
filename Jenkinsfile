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
            cleanWs()
        }
        stage(GIT){
            git branch: 'main', url: 'https://github.com/RukhsanaBegm/spring-petclinic'
        }

        stage(build) {
            sh(script: 'mvn package')

        }
        stage(archiveArtifacts) {
            archiveArtifacts(artifacts: '**/*.jar')
        }

    }


}