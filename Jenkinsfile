@Library('slack')
import slack.Slack

Slack slack = new Slack();

node('master'){
    slack.slackNotification('start')
    stage('test'){
        echo "run tests"
        try {
            sh 'yum list installed | grep kernel'
            echo "inside the try statement"
        }
        catch (Exception err) {
            slack.sendNotification('fail')
            currentBuild.result = 'FAILURE'
            throw error
        }
    }
    stage('build'){
        echo "run build"
    }
    slack.slackNotification('ok')
}