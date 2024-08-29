# Jenkins-GitHub Integration with Ngrok

## Prerequisites

- Ngrok: Download and install ngrok from [ngrok.com](https://ngrok.com/).
- Jenkins: Ensure Jenkins is running and configured with the necessary plugins, including Multibranch Pipeline Scan Trigger Plugin.
- GitHub: Have your repository set up on GitHub.

## Steps

1. **Expose Jenkins with Ngrok:**
   - Open Terminal window and run `ngrok http 8080`, this will create a secure tunnel and provide you with a public URL that points to your Jenkins server.

2. **Create Multibranch Pipeline in Jenkins:**
   - Go to your Jenkins Dashboard.
   - Click on **New Item** to create a new Job.
   - Give a display name for your project.
   - In the Branch source section, Click on add resource dropdown and select single repository and branch.
   - Paste your GitHub repository URL in the Repository URL field and also specify the branch you want to monitor.
   - Under **Advanced**, check the box for **Scan by webhook** and give it a secret token `[myToken]`. This token will be used in the next step to secure webhook connections.
   - Click **Apply** and then **Save**.

3. **Create a webhook in GitHub:**
   - Go to your GitHub repository settings.
   - Navigate to the **Webhooks** section.
   - Click **Add webhook**.
     - **Payload URL**: Enter the public URL provided by ngrok in step 1 (`ngrok_url/multibranch-webhook-trigger/invoke?token=[myToken]`).
     - Change content type to **application/json**.
     - Events: Choose the events you want to trigger the webhook (e.g., push, pull request).
     - Check the active checkbox and click **Add webhook**.

4. **Testing:**
   - Make some changes in your code and push it to GitHub.
   - Jenkins should receive a notification from GitHub and automatically trigger a build for the corresponding branch.
   - You can monitor the build progress in the Jenkins console or build history.

