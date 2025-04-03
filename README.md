# Telegram Notification Workflow Test

This is a sample project to test GitHub Actions workflows that send Telegram notifications.

## Setup

1. Fork this repository
2. Add the following secrets to your repository settings:
   - `TELEGRAM_TO`: Your Telegram chat ID (can be a user ID or channel ID)
   - `TELEGRAM_TOKEN`: Your Telegram bot token

## Testing the Workflow

The project contains three GitHub Actions workflows:

1. `telegram-notification.yml` - Sends notifications when deployment workflows complete
2. `deploy-prod.yml` - Simulates a production deployment
3. `deploy-prod-from-branch.yml` - Simulates a deployment from a specific branch

### How to Test

1. Run the "Deploy Explorer - PROD" workflow manually from the Actions tab
2. Wait for it to complete
3. The "Telegram Notification" workflow should trigger automatically
4. Check your Telegram chat to see the notification message

Alternatively, you can run the "Deploy Explorer - PROD - From Branch" workflow and specify a branch name.

## Workflow Details

- The notification workflow triggers when either of the deployment workflows completes
- It sends a formatted Markdown message to your Telegram chat
- The message includes details about the workflow run, status, branch, and more

## Expected Result

You should receive a Telegram message containing:
- Workflow name
- Status (Success, Failed, or Cancelled)
- Branch/Tag information
- Triggered by user
- Repository name
- URL to the workflow run 