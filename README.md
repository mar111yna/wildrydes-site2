How to deploy on AWS:

Create TTTAdmin user with admin access rights
open IAM service
Left pane→Access Management→Users→TTTAdmin→Permissions → Add permissions →Attach policies directly →AWSCodeCommitPowerUser → Next → Add permissions

Create Git credentials for this IAM user to allow HTTPS connections to Github

Left pane→Access Management→Users→TTTAdmin→Security credentials → HTTPS Git credentials for AWS CodeCommit → Generate credentials → Download credendials → Close 


Clone the repository:
Copy github repo URL
Top pane→ AWS CloudShell 
```
$ git clone <name of your newly created empty repo>
For username: <Enter your username on git>
For password: <Enter your generated token on git>
$ cd  wildrydes-site2 
$ (add files from this repo)
$ git add . 
$ git commit -m “Initial commit” 
$ git push
For username: <Enter your username on TTTAdmin HTTPS credentials>
For password: <Enter your TTTAdmin HTTPS password>
```

Search for AWS Amplify
Click “New app”
Click Git
Click “Authorize AWS Amplify”
Click “Install and Authorize”
Choose repo ->click Next → Save and Deploy


Search for Cognito
Create user pool→Cognito user pool (checkmark on Username)- >Next → Cognito defaults (No MFA, Enable self service account, Email only) - > Next → Enable self- registration (Allow Cognito to auto send messages to verify → Send email with Cognito → Next → UserPoolName: WildRydes2 (App client name: WildRydesWebApp, Dont generate a client secret) → Create user pool

Copy Client Id under “App clients and Analytics”

register on the website of your app and verify email
save auth token it will show


...
Tutorial TBC
