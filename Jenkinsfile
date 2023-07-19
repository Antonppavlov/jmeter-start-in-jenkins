#!groovy
pipeline {
    agent any
    stages {

//        stage('Start Notifications') {
//            steps {
//                echo "Sending Email Notification"
//            }
//            post {
//                always {
//                    echo "STARTED - Performance Tests"
//                    mail(to: 'username@srv.net', from: "jenkins@srv.net", subject: "START - Performance Tests", mimeType: "text/html", body: "<strong>START - Performance Tests</strong><br /><br />Project: Name of Project<br />Environment: PerfTest<br />Build number: ${env.BUILD_NUMBER}<br />Build URL:   ${env.BUILD_URL}"
//                }
//            }
//        }

        stage('Git checkout') {
            steps {
                git 'https://github.com/Antonppavlov/jmeter-start-in-jenkins.git'
            }
        }

        stage('Jmeter checkout') {
            steps {
                script{
                    try {
                        def jmeterAlreadyInstall = sh(script: 'cd apache-jmeter-5.6.2/bin', returnStdout: true).trim()
                    } catch (Exception ex) {
                        echo 'Install Jmeter'

                        script {
                            sh '''
                                curl https://dlcdn.apache.org//jmeter/binaries/apache-jmeter-5.6.2.tgz -o apache-jmeter-5.6.2.tgz;
                                tar -xvzf apache-jmeter-5.6.2.tgz;
                               '''
                        }
                    }
                }
            }
        }


        stage('Start Performance Tests') {
            steps {
                script {
                    sh '''
                        pwd; ls -ltrh;
                        java -version;
                        cd apache-jmeter-5.6.2/bin;
                        sh jmeter.sh -n -t ../../jmeter_start_in_jenkins.jmx -l result.jtl -Jhost=wordpress
                    '''
                }
            }
        }

        stage('Publish Performance test result report') {
            steps {
                perfReport filterRegex: '', showTrendGraphs: true, sourceDataFiles: 'apache-jmeter-5.6.2/bin/result.jtl'
            }
        }

//        post {
//            failure {
//                echo "FAILED - Performance Tests"
//                mail(to: 'username@srv.net', from: "jenkins@srv.net", subject: "FAILED - Performance Tests",mimeType: "text/html", body: "<strong>FAILED - Performance Tests</strong><br /><br />Project: Name of Project<br />Environment: PerfTest<br />Build number: ${env.BUILD_NUMBER}<br />Build URL: ${env.BUILD_URL}"
//            }
//
//            success {
//                echo "SUCCESSED - Performance Tests"
//                mail(to: 'username@srv.net', from: "jenkins@srv.net", subject: "SUCCESSED - Performance Tests",mimeType: "text/html", body: "<strong>SUCCESSED - Performance Tests</strong><br /><br />Project: Name of Project<br />Environment: PerfTest<br />Build number: ${env.BUILD_NUMBER}<br />Build URL:   ${env.BUILD_URL}"
//            }
//        }

    }
}