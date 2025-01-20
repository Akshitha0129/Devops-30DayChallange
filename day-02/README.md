# 30-Day DevOps Challenge | Day 2

Creating a Game Day Notification solution using AWS Lambda, Amazon SNS, and Amazon EventBridge with external APIs.
Building a Game Day Notification solution using AWS serverless services such as AWS Lambda, Amazon SNS, and Amazon EventBridge, while integrating external APIs to deliver notifications effectively.

<img width="739" alt="Screenshot 2025-01-08 at 2 40 09 AM" src="https://github.com/user-attachments/assets/b6e8961d-cc00-4d8f-a5ba-f0eb8da3737c" />

Solution Architecture

1. AWS Lambda:
Fetches game data from an external API (e.g., sports data API).
Processes the response and formats the notification.

2. Amazon EventBridge:
Schedules the Lambda function to run at specific intervals (e.g., daily at 9 AM or before a game starts).

3. Amazon SNS:
Sends notifications (email/SMS) to subscribers about game details.

4. External API:
Provides game data, such as teams, scores, schedules, or player stats.

Prerequisites:
To get started, you need:
A free account and API key from SportsData.io.
An AWS account with a basic understanding of AWS services and Python programming.

Technical Architecture:
The architecture leverages AWS serverless services to provide a seamless, cost-effective solution. Here's how the system works:
Amazon EventBridge triggers the notification workflow based on a predefined schedule.
AWS Lambda retrieves live game scores using the NBA Game API and processes the data.
The formatted scores are published to Amazon SNS, which distributes notifications to subscribed users via email or SMS.

Technologies Used:
Cloud Provider: AWS
Core AWS Services: Amazon SNS, AWS Lambda, Amazon EventBridge
Programming Language: Python 3.x
External API: NBA Game API from SportsData.io
IAM Security: Least privilege policies for Lambda, SNS, and EventBridge

Step-by-Step Setup Instructions
1. Clone the Repository
cd game-day-notifications
2. Create an SNS Topic
Open the AWS Management Console.
Navigate to Amazon SNS.
Create a topic with type Standard and note the ARN.

3. Add Subscriptions to the SNS Topic
For Email: Enter a valid email address and confirm the subscription via email.
For SMS: Enter a valid phone number in international format (e.g., +1234567890).

4. Create an SNS Publish Policy
Navigate to IAM Policies in AWS Management Console.
Create a policy using gb_sns_policy.json, replacing placeholders with your AWS region and account ID

5. Create an IAM Role for Lambda
Assign the SNS Publish Policy and the AWS-managed AWSLambdaBasicExecutionRole to the role.
Save the ARN of the role for later use.

6. Deploy the Lambda Function
Create a Lambda function in AWS with Python 3.x as the runtime.
Assign the IAM role created earlier.
Paste the code from src/gd_notifications.py into the inline editor.
Set the following environment variables:

NBA_API_KEY: Your NBA API key.
SNS_TOPIC_ARN: ARN of the SNS topic created earlier.

7. Automate with EventBridge
Create a rule in EventBridge with a scheduled cron expression for hourly updates.
Set the target as the Lambda function.

<img width="460" alt="Screenshot 2025-01-08 at 2 27 31 AM" src="https://github.com/user-attachments/assets/7d839e85-7d36-45c4-bdf0-a6168981401d" />

9. Test the System
Trigger the Lambda function manually.
Check for notifications in email or SMS.
Debug errors using CloudWatch Logs.

<img width="485" alt="Screenshot 2025-01-08 at 2 58 56 AM" src="https://github.com/user-attachments/assets/8ac59d6a-97e1-40a9-9f35-437f61bd31f7" />


