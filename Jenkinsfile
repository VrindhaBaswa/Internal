pipeline{
    agent any{
        stages{
            stage('compile'){
                steps{
                    bat 'javac Factorial.java Test Factorial.java'
                }
            }
            stage('Test'){
                steps{
                    bat 'java Test Factorial.java'
                }
            }
            stage('Run'){
                steps{
                    bat 'java Factorial.java'
                }
            }
            stage('package jar'){
                steps{
                    bat 'jar cfm factorial.jar Factorial.class'
                }
            }
            stage('Archieve Jar'){
                steps{
                    bat 'archieveArtifacts artifacts: factorial.jar'
                }
            }
            post{
                success{
                    echo 'Build,test,run and JAR successful & artifact is ready'
                }
                failure{
                    echo 'failed'
                }
            }
        }
    }
