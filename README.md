### discourse-azure-oauth2

A Discourse plugin to enable login Microsoft Azure Active Directory users via OAuth2.


### Configuration

Add your Discourse site as an application in Windows Azure Active Directory (WAAD). [Follow instructions here](https://msdn.microsoft.com/en-us/library/azure/dn132599.aspx), and use the following values:

* Name is not important.
* Choose "Web Application and/or Web API" as the application type.
* Sign-On URL (aka Reply URL): enter the full URL with path `/auth/azure_oauth2/callback`. e.g., `http://discourse.example.com/auth/azure_oauth2/callback`
* App ID URI: use the root url of your Discourse site. e.g., `http://discourse.example.com`
* Click on the new app, choose Configure from the top nav, and generate a new key in the "Keys" section.
* In the Configure section, you'll find the Client ID, and the key that you generated will be used as the clients secret. Also make sure that the Reply URL is the full url to /auth/azure_oauth2/callback.

Add the following to your `discourse.conf` file:

* azure_oauth2_client_id
* azure_oauth2_client_secret
* (optional) azure_oauth2_title


### Future Work

* Multi-tenant support