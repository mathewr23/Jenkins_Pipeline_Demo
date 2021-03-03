pipeline {
  agent any
    stages {
        stage('#1 Configure, build, & deploy the WebDriverAgent.xcodeproj onto the iOS device') {
          steps {
            sh '''
              cd /usr/local/lib/node_modules/appium/node_modules/appium-webdriveragent/
              mkdir -p Resources/WebDriverAgent.bundle
              ./Scripts/bootstrap.sh -d
              echo "# 2 Deploy the WebDriverAgentRunner app onto the test device"
              xcodebuild -project WebDriverAgent.xcodeproj -scheme WebDriverAgentRunner -destination 'id=68ba5756cb40cfaaeb8830d8b54be26ad441cb5c' test
            '''
          }
        }
      stage('#2 Launch Selenium Hub') {
        steps {
          sh '''
            java -jar /Users/iosautomation/Documents/iOSAutomation/eclipse-workspace/WWOneAppFunctionalAutomation/selenium-server-standalone-3.4.0.jar -role hub -host 169.254.212.18 -port 4444
            
          '''
        }
      stage('#3 Launch Appium Server and target the iOS device') {
        steps {
          sh '''
            main.js --address 127.0.0.1 --port 4729 --nodeconfig /Users/iosautomation/Documents/iOSAutomation/eclipse-workspace/WWOneAppFunctionalAutomation/ServerConfig/node-WooliesIphone.json --session-override
          '''
        }
      }
    }
}
