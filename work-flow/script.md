Useful script

pod install && open JIRA.xcworkspace
xctool test && git push origin HEAD

xctool test && git push origin HEAD && terminal-notifier -message "Tested & Pushed to origin" && open "https://stash.atlassian.com/projects/MOB/repos/jira-ios/pull-requests?create"

git merge master && git submodule update && pod install && xctool test && git add -u . && open .xcwork

grep 'com.apple.Push = {\n\s+enabled = 1;\n\s+};' JIRA.xcodeproj/project.pbxproj
grep 'enabled = 1;' JIRA.xcodeproj/project.pbxproj


rake release:make\["1.1.1"\] && rake release:alpha:ship && open "https://hipchat-bamboo.internal.atlassian.com/browse/APL-CIOS0-15"

https://ios.jira-dev.com/secure/viewavatar?size=normal@2x&avatarId=10303&format=PNG&avatarType=issuetype
https://ios.jira-dev.com/secure/viewavatar?size=xsmall&avatarId=10303&avatarType=issuetype
