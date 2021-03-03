# Let's automate the iOS Functional Automation Projects' setup process by using Jenkins!

## Setup will fail if:
1. The **WebdriverAgentRunner** *target* in the **WebDirverAgent** *project* has not been signed with a valid Apple Development signing certificate. Let Xcode manage the provisioning profile.
2. The certificate for the **WebDriverAgentRunner** *app* is not *trusted* on the physical test device (in the devices *settings* app) after it gets installed.

## Things to check:
1. If the **WebDriverAgentRunner** *app* has been previously installed and trusted... will Jenkins succeed first time round? Probably!
