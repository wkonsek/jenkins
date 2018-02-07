@Library('slack')
import slack.Slack

Slack slack = new Slack();

node('master'){
    slack.sendNotification('start')
    stage('test'){
        echo "run tests"
        try {
            sh 'echo "Hello from the Docker"'
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
    slack.sendNotification('ok')
    
}