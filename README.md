# Cisco Impact DevNet Express SASE Session
http://cs.co/devnetsase-impact23

Welcome!  This workshop is a sample of the **brand new** Security DevNet Express content available to you, your customers, and your partners.  This module will introduce you to some simple ways we can use automation to manage, deploy, and monitor SSE and SASE solutions.  You will be using **two** resources for these exercises, the DevNet Express 2.0 Learning Lab environment and a Cisco SASE v2 dCloud Lab.

<img width="1420" alt="DNE" src="https://user-images.githubusercontent.com/10421515/185941156-3632b79c-24fb-4e08-903d-617d8400bd04.png">

- - -
**Quick Access**
- [Accessing Your SASE Environment](#accessing-your-sase-environment)
  * [Your DevNet Learning Lab 2.0 Environment](#your-devnet-learning-lab-20-environment)
- [Setting up your SASE Environment and Introduction to Duo](#setting-up-your-sase-environment-and-introduction-to-duo)
    + [Creating, Reading and Deleting Duo Users with the API](#creating--reading-and-deleting-duo-users-with-the-api)
- [Setting up your Umbrella Environment and Intro to Umbrella Management API](#setting-up-your-umbrella-environment-and-intro-to-umbrella-management-api)
    + [Hands on with Umbrella Network Tunnel Management API](#hands-on-with-umbrella-network-tunnel-management-api)
- [SASE Integration: Umbrella and Duo](#sase-integration-umbrella-and-duo)
- - -

## Accessing Your SASE Environment

1. Access your dCloud Lab Environment here: 
> Use an incognito or private window to access the lab environment!
> https://dcloud.cisco.com/expo/16r4tlz2xklhv16lxp5ue0lu1

## Your DevNet Learning Lab 2.0 Environment

The learning environment uses containers and doesn't require a dedicated development environment as we did for DevNet Express 1.0 and 1.1. The foundation of this workshop available here: https://developer.cisco.com/learning/tracks/devnet-express-security/security-sase/.  Open this page in a new window and authenticate using one of the available federations.

<img width="1420" alt="Interface" src="https://user-images.githubusercontent.com/10421515/185941577-b6b1b9af-b9a9-4265-9ac3-0fd17a16cbd0.png">

You will be using the IDE to write your code and the terminal below will execute the Python scripts.

If you get stuck, need a hint, or just want to jump to the answer, all of the solutions are posted as part of the environment in `~/src/solutions/sase` folder.

<img width="705" alt="solutions" src="https://user-images.githubusercontent.com/10421515/185953534-ffd030c9-3a18-44da-b74e-9e5cb33758b1.png">

## Setting up your SASE Environment and Introduction to Duo

<img width="397" alt="Intro to Duo" src="https://user-images.githubusercontent.com/10421515/185945491-b5a060f1-7286-4697-b931-dcb168e6f101.png">

1. Follow these steps to initialize your Duo Admin User and generate an API Key for this lab. 
> https://developer.cisco.com/learning/tracks/devnet-express-security/security-sase/sase-1-setup/how-to-set-up-your-sase-environment/

* Initialize your Duo Admin Panel and authenticate your new admin user
* Setup an Admin API key for use in the learning environment
* **COPY API KEY LOCALLY. YOU WILL NEED IT FOR THIS EXERCISE**

### Creating, Reading and Deleting Duo Users with the API

<img width="396" alt="Create and Delete" src="https://user-images.githubusercontent.com/10421515/185946774-c883e8da-0569-4476-bca2-0aae2042a1f8.png">

Complete steps 3 and 4 using the Learning Lab Environment.

> **Note**
> You will need to use the API key YOU GENERATED to see the results in your environment.  Replace the following lines at the top of your Python script to use your API key rather than the one included in the Learning Environment.

REPLACE THIS!
``` python
import environment as env
duo_integration_key = env.DUO_INTEGRATION_KEY
duo_secret_key = env.DUO_SECRET_KEY
duo_api_host = env.DUO_API_HOST
```
WITH THIS!
``` python
import environment as env
duo_integration_key = 'YOUR API KEY'
duo_secret_key = 'YOUR SECRET KEY'
duo_api_host = 'api-demodemo.duosecurity.com'
```
You will accomplish the following items at the conclusion of the module:

* Writing a python script that programmatically adds a new user 'granite' to the Duo Users.
* Disables the 'granite' user using the API.
* Re-enables the 'granite' user using the API.

## Setting up your Umbrella Environment and Intro to Umbrella Management API

1. Follow these steps to initialize your Duo Admin User and generate an API Key for this lab. 
> https://developer.cisco.com/learning/tracks/devnet-express-security/security-sase/sase-5-umbrella-tunnels/introduction/

2. Generate your Umbrella Management API Key in the Cisco SASE v2 lab.  Click on the **Demo Ready** icon on the desktop.

<img width="1420" alt="desktop" src="https://user-images.githubusercontent.com/10421515/185956910-f0d5f5f3-4712-4018-8071-93a9ea0d0efe.png">

3. Access the Umbrella console from the resulting page.

<img width="1420" alt="demo ready" src="https://user-images.githubusercontent.com/10421515/185957126-907214ce-45ed-4034-9305-f0676c7034c8.png">

4. Navigate to **Admin -> API Keys**, find Umbrella Management and click **Generate Token**.

<img width="1420" alt="umbrella api" src="https://user-images.githubusercontent.com/10421515/185957674-0f22c3c3-86c0-4f76-b76b-8b6d00e1b6c8.png">

* **COPY API KEY AND SECRET LOCALLY. YOU WILL NEED IT FOR THIS EXERCISE**

### Hands on with Umbrella Network Tunnel Management API

Complete steps 3 and 4 in the Learning Lab environment.

<img width="392" alt="tunnel api" src="https://user-images.githubusercontent.com/10421515/185958539-b1edf37b-fe92-454d-a15a-a03f6afe99d3.png">

> **Note**
> You will need to use the API key YOU GENERATED to see the results in your environment.  Replace the following lines at the top of your Python script to use your API key rather than the one included in the Learning Environment.  You will also need your organization ID from the dCloud lab.  You can find it in the URL for the Umbrella console as referenced in the image below.

<img width="1420" alt="orgid" src="https://user-images.githubusercontent.com/10421515/185959779-650f05d6-4106-4df0-aced-d504d70cb361.png">

REPLACE THIS!
``` python
# set global variables
token_url = "https://management.api.umbrella.com/auth/v2/oauth2/token"
umb_client_id = env.UMBRELLA_MANAGEMENT_KEY
umb_client_secret = env.UMBRELLA_MANAGEMENT_SECRET
umb_org_id = env.UMBRELLA_ORG_ID
```
WITH THIS!
``` python
# set global variables
token_url = "https://management.api.umbrella.com/auth/v2/oauth2/token"
umb_client_id = 'YOUR MANAGEMENT API KEY'
umb_client_secret = 'YOUR MANAGEMENT SECRET KEY'
umb_org_id = 'YOUR ORG ID'
```

When creating the tunnel, you will need to choose a unique tunnel name, define an idPrefix string, and secret.  A pre-defined secret is included.

> **Note**
> **The idPrefix variable MUST BE AT LEAST 8 CHARACTERS when creating the tunnel definition.**

You will accomplish the following items at the conclusion of the module:

* Automating the creation of tunnel interfaces into Umbrella using the Umbrella Management API.
* Querying details about the tunnel interfaces.
* Seeing the built tunnels on the Umbrella Console

## SASE Integration: Umbrella and Duo

1. Return to the Umbrella Console and generate a Reporting API Key.  This can be found in **Admin -> API Keys** then Umbrella Reporting.

<img width="1420" alt="reporting" src="https://user-images.githubusercontent.com/10421515/185997667-4444dec5-5984-4d39-b6a6-f771ec8438a3.png">

* **COPY API KEY AND SECRET LOCALLY. YOU WILL NEED IT FOR THIS EXERCISE**

2. Create a Python script that will look at Umbrella security events from the previous 7 days and disable associated users accounts in Duo.

3. Follow the steps outlined in the Learning Lab: https://developer.cisco.com/learning/tracks/devnet-express-security/security-sase/sase-7-umbrella-duo/introduction/

<img width="397" alt="integration" src="https://user-images.githubusercontent.com/10421515/185967873-37e0293d-f18f-4958-8814-88573857aa17.png">

* While building the script using the lab guide, be sure to replace the API keys and Umbrella environment with those from your dCloud instance.

REPLACE THIS!
``` python
# import script constants
duo_integration_key = env.DUO_INTEGRATION_KEY
duo_secret_key = env.DUO_SECRET_KEY
duo_api_host = env.DUO_API_HOST
umb_token_url = "https://management.api.umbrella.com/auth/v2/oauth2/token"
umb_client_id = env.UMBRELLA_REPORTING_KEY
umb_client_secret = env.UMBRELLA_REPORTING_SECRET
umb_org_id = env.UMBRELLA_ORG_ID
```
WITH THIS!
``` python
# import script constants
duo_integration_key = 'YOUR DUO API KEY'
duo_secret_key = 'YOUR DUO SECRET KEY'
duo_api_host = env.DUO_API_HOST
umb_token_url = "https://management.api.umbrella.com/auth/v2/oauth2/token"
umb_client_id = 'YOUR UMBRELLA REPORTING API KEY'
umb_client_secret = 'YOUR UMBRELLA REPORTING SECRET KEY'
umb_org_id = 'YOUR UMBRELLA ORG ID'
```
## Conclusion

Thank you for taking time at Impact to learn about our new seecurity DevNet Express content and programmability for our SASE solution.  If you'd like to schedule an event for your customers, partners, or your team, please reach out to me.  

Have a great Impact event!

