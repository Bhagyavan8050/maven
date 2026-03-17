pipeline {
    agent any

    tools {
        // maven 'MAVEN_HOME'
        maven 'MAVEN_HOME' // Make sure this matches your Jenkins global tool config
    }

    stages {
        stage('Welcome Stage') {
            steps {
                echo "Welcome to Pipeline"
            }
        }

        stage('Maven Build') {
            steps {
                bat 'mvn install'
                bat 'mvn clean install' // Includes test by default
            }
        }

        stage('Run Tests') {
            steps {
                echo "Running Unit Tests"
                // Optional: You can explicitly run 'mvn test' here
                bat 'mvn test'
            }
        }

        stage('Publish Test Results') {
            steps {
                junit 'target/surefire-reports/*.xml' // Standard JUnit report location for Maven
            }
        }

        stage('Build Successs') {
            steps {
                echo "Build Successful"
            }
        }
    }
}

// pipeline {
//     agent any
//
//     stages {
//
//         stage('Build') {
//             steps {
//                 echo "Building Maven Project"
//                 sh 'mvn clean package'
//             }
//         }
//
//         stage('Deploy to Dev') {
//             when {
//                 branch 'b1'
//             }
//             steps {
//                 echo "Deploying to Dev Environment"
//             }
//         }
//
//         stage('Deploy to Production') {
//             when {
//                 branch 'master'
//             }
//             steps {
//                 echo "Deploying to Production Environment"
//             }
//         }
//
//     }
// }
