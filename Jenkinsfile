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

//        stage('Git checkout') {
//            steps {
//                git 'https://github.com/Antonppavlov/jmeter-start-in-jenkins.git'
//            }
//        }

        stage('Jmeter checkout') {
            steps {
                script {
                    def GString jmeterAlreadyInstall = sh(script: "cd apache-jmeter-5.6.2/bin;", returnStdout: true).trim()
                    echo jmeterAlreadyInstall
//                    if (jmeterAlreadyInstall.contains('can\'t cd to apache-jmeter' as java.lang.CharSequence)) {
//                        echo 'Hello from main branch'
//                        sh
//                        '''
//                            pwd; ls -ltrh;
//                            java -version;
//                            cd apache-jmeter-5.6.2/bin;
//                            sh jmeter.sh -n -t ../../jmeter_start_in_jenkins.jmx -l result.jtl -Jhost=wordpress
//                        '''
//                    } else {
//                        sh "echo 'Hello from ${env.BRANCH_NAME} branch!'"
//                    }

                }
            }
        }

//        stage('Perf Tests') {
//            steps {
//                script {
//                    sh '''
//                        pwd; ls -ltrh;
//                        java -version;
//                        cd apache-jmeter-5.6.2/bin;
//                        sh jmeter.sh -n -t ../../jmeter_start_in_jenkins.jmx -l result.jtl -Jhost=wordpress
//                    '''
//                }
//            }
//        }

//        stage('Publish Performance test result report') {
//            steps {
//                perfReport filterRegex: '', showTrendGraphs: true, sourceDataFiles: 'apache-jmeter-5.6.2/bin/result.jtl'
//            }
//        }

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