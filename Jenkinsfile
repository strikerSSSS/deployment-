pipeline {
    agent any

    stages {
        stage('clone from github(GitHubBuild)') {
            steps {
                git branch: 'master', url: 'https://github.com/strikerSSSS/deployment-.git'
            }
        }
        stage('build war file(MavenBuild)') {
            steps {
                sh "mvn clean install package"
            }
        }
        stage('deploy to tomcat(DeployBuild)') {
            steps {
                sh "sudo scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/tom/webapp/target/webapp.war root@ 100.25.129.172:/root/apache-tomcat-9.0.86/webapps"
            }
        }
    }
}
