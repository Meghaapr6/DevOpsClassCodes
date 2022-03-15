pipeline{
    
    tools{
        jdk 'myjava'
        maven 'mymaven'
    }
    agent any
    stages{
        stage('Clone a repo')
        {
            steps{
                git 'https://github.com/Sonal0409/DevOpsClassCodes.git'
            }
        }
        stage('Compile'){
            
            steps{
                sh 'mvn compile'
            }
        }
        
        stage('CodeReview')
        {
        steps{
            sh 'mvn pmd:pmd'
        }
    }
    stage('Unit Test'){
        steps{
            sh 'mvn test'
        }
    }
    
    stage('CodeCoverage'){
        steps{
            sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
        }
    }
    
    stage('package'){
        steps{
            sh 'mvn package'
        }
    }
    
    
    }
    
}
