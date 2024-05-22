# Okta React + Okta Hosted Login Example

1.Register an account on website: https://developer.okta.com/login/ (Need work email).Instead, we can download  "okta for windows"(https://github.com/okta/okta-cli/releases) to resiger an account with personal email<br/>
1.1 If we use "okta for windows", unzip the downloaded zip file and put okta.exe into a folder, then enter the folder using cmd:
    okta register
2.Login the website: https://developer.okta.com/login/, then click "Applications"->"Applications" to create app integration, choose "oidc" and "Single-Page Application" to generate a react app. Note down the client id and domain. 

3. Set up the settings:
    Sign-in redirect URIs: http://localhost:3000/login/callback
    Sign-out redirect URIs: http://localhost:3000
    Grant type: "Authorization Code" and "Refersh Token"
    Assignments->Controlled access: Allow everyone in your organization to access

4. Add one person on the Directory->people

5. Use the following command to create a react app:
    okta start
    5.1 choose the number 6 to create a react app.
6. Open the app using vscode 
6.1 Modify  CLIENT_ID and ISSUER in the .okta.env file
6.2 Modify the CLIENT_ID and ISSUER of config.js (Just in case the configuration of .okta.env doesn't work if we don't install dotenv dependencies).See the below description:
    const CLIENT_ID = process.env.CLIENT_ID || '0oah98fyx3DtHkknK5d7';
    const ISSUER = process.env.ISSUER || 'https://dev-85274789.okta.com/oauth2/default';
7. Use "npm install" to install dependencies.
8. Use npm start to run the app
9. Click the login button and forward to "okta" sign in page, then input the user name and password that created on step 4.
10.Check the localstorage to see the idtoken.

