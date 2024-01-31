# Bitbucket Data Center / Server Integration Setup (OAuth 1)
## Private Packagist Self-Hosted

## Initial Setup
Hit the “Add integration“ button on the admin page to get to the form below. To setup a Bitbucket Data Center / Server integration with Private Packagist start by selecting "Bitbucket Data Center / Server" as the platform, OAuth 1 as OAuth version, and enter the URL of your on-premise Bitbucket Server into the base URL field as seen in the example below.

![Packagist Setup](/Resources/public/img/docs/integration-setup/bitbucket-server-oauth1-01-packagist-setup.png)

Submit the form to see the additional information.

![Packagist Form](/Resources/public/img/docs/integration-setup/bitbucket-server-oauth1-02-packagist-form.png)

## Configure Application link
Click on the link to setup an Application Link on Bitbucket Data Center / Server. You will need the "Client Id" and the "Public Key" shown in the form.

![Bitbucket Configure Application Link](/Resources/public/img/docs/integration-setup/bitbucket-server-oauth1-03-bitbucket-configure-application-link.png)

For Bitbucket Data Center versions 7.21 and newer, select "Atlassian product" and not "External application" to be able to set up an OAuth1 link.

After you hit the button to create a new Application Link a configuration window may appear. If it does, verify that the url matches your Private Packagist URL and hit "Continue", otherwise skip this step.

![Bitbucket Invalid Url](/Resources/public/img/docs/integration-setup/bitbucket-server-oauth1-04-bitbucket-invalid-url.png)

Now setup a "Generic Application". The only field required is the "Application Name". Submit the form to finish creating the Application Link.

![Bitbucket Setup Link](/Resources/public/img/docs/integration-setup/bitbucket-server-oauth1-05-bitbucket-setup-link.png)

![Bitbucket Application Created](/Resources/public/img/docs/integration-setup/bitbucket-server-oauth1-06-bitbucket-application-created.png)

Click on the pen icon to the right of the application you just created to edit the Application Link and configure Incoming Authentication.

![Bitbucket Incoming Auth](/Resources/public/img/docs/integration-setup/bitbucket-server-oauth1-07-bitbucket-incoming-auth.png)

This is where we will need the "Client ID" and the "Public Key" that were previously generated on the Private Packagist integration form. Make sure the entire content of the "Public Key" field gets copied and the "Consumer Callback" field stays empty. Submit the form and go back to Private Packagist.

## Finish the Setup
Update the Integration on Private Packagist to save everything and finish the setup.

![Packagist Finalize](/Resources/public/img/docs/integration-setup/bitbucket-server-oauth1-08-packagist-finalize.png)

## Configure Bitbucket Server plugins

In case the U2F & TOTP plugin by Alpha Server is installed on the Bitbucket Server then you will need to enable the OAuth whitelist
otherwise Private Packagist will not be able to authenticate with the Bitbucket Server.

![Bitbucket Server TFA Configuration](/Resources/public/img/docs/integration-setup/bitbucket-server-09-tfa.png)
