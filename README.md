<h1>DOTS Tool Guide</h1>

<p>This directory is a guide to help user(s) integrate tools and also add/manage user(s)</p>

- [Jenkins and Slack Integration](#Jenkins-And-Slack-Integration)
    * [How to activate 2FA(Two-Factor-Authentication) Slack workspace and integrate with Jenkins](#How-to-activate-2FA-Slack-workspace-and-integrate-with-Jenkins)
        * [Test Integration](#Test-Integration)


## Jenkins And Slack Integration

### How to activate 2FA Slack workspace and integrate with Jenkins
  <ol>
    <li>Activate 2FA(Two-Factor-Authentication) Slack workspace</li>
        <ol>
          <li>Create a slack workspace</li>
            <ul>
              <li><a href="https://slack.com/help/articles/206845317-Create-a-Slack-workspace">Documentation to create a workspace</a></li>
            </ul>
          <li><a href="https://github.com/hnnguye5/DOTS_CDIT/blob/master/pics/workspace_setting.png?raw=true">Go to your                  workspace settings</a></li>
          <li><a href="https://github.com/hnnguye5/DOTS_CDIT/blob/master/pics/workspace_wide_two_factor.png?raw=true">Click on            the Authentication tab. Then click on expand for Workspace-wide two-factor authentication</a></li>
          <li>Check your email to received more information from Slack to authenticate your Slack account</li>
        </ol>
    <li>Integrate with Jenkins</li>
      <ol>
        <li>Generate a Slack Token</li>
          <ol>
            <li>Navigate to <a href="https://testjenkinsspace.slack.com/apps/A0F7VRFKN-jenkins-ci?next_id=0">Jenkins CI</a>               </li>
            <li>Click Add to Slack and choose to channel to allow Jenkins to post notifications</li>
            <li>Copy the token and head back to Jenkins Homepage</li>
            <li>Click on Credentials ---> System ---> Global credentials(unrestricted) ---> Add Credentials</li>
            <li>In Kind dropdown box, select Secret Text and paste your token in Secret and give an ID and description</li>
          </ol>
       <li>Return to Jenkins homepage and click on Manage Jenkins ---> Configure Systems.</li>
       <li>Head to the Slack section and enter the workspace information, click the dropdown menu for the correct                     credentials, and enter the name of the channel. (if no credential is available, you must create one)</li>
         <ul>
           <li>If no credential is available, you must create one</li>
            <ol>
              <li>Click on Add and then Jenkins</li>
              <li>In Kind dropdown box, select Secret Text and paste your token in Secret and give an ID and description</li>
              <li>Click on Add</li>
              <li>Ensure the credentials you just created is selected</li>
            </ol>
         </ul>
       <li>Click Test Connection and make sure it is successful. Then scroll down and click Apply and then Save</li>
      </ol>
  </ol>

  ### Test-Integration
        <ol>
          <li>Click on New Item</li>
          <li>Give it a name and use Pipeline</li>
          <li>Under Pipeline, enter the script to send a message to Slack</li>
             <ul>
              <li><a href="https://github.com/hnnguye5/DOTS_CDIT/blob/master/pics/slack-message.png?raw=true">Script Example</a></li>
            </ul>
          <li>Go back to Jenkins homepage and click on Manage Jenkins --> Manage Plugins</li>
          <li>Under Available tab, search for Slack Notification and Pipeline. Click the checkbox next to their names. Then             click Install without Restart</li>
          <li>Return back to your Jenkins homepage and click on the name of your pipeline</li>
          <li>Click on Build Now</li>
           <li>Check your Slack workspace to see a new message</li>
       </ol>
