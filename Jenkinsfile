pipeline {
    agent any
    
    stages {
        stage('Git-checkout') {
            steps {
                git branch: 'main', credentialsId: 'gokhantanisik-gmail.com-ssh_key_id', url: 'git@github.com:gtanisik/jenkins_experiments.git'
            }
        }
        
        stage('compile') {
            steps {
                cmakeBuild buildDir: 'build', cleanBuild: true, installation: 'InSearchPath'
            }
        }
        
        stage('test') {
            steps {
                echo "test"
            }
        }
        
        stage("quality") {
            steps {
                echo "quality"
            }
        }
        
        stage("deploy") {
            steps {
                echo "deploy"
            }
        }
    }
    
    post {
        always {
            echo "this will always run"
        }
        
        success {
            echo "this will run on success"
        }
        
        failure {
            echo "this will run on failure"
        }
        
        unstable {
            echo "this will run if the run was marked unstable"
        }
        
        changed {
            echo "this will run only if the state of the pipeline has changed"
            echo "for example, if the pipeline was previously failing but is now successful"
        }
    }
}
