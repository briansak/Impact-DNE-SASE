# Cisco Impact DevNet Express SASE Session

Welcome!  This session is a sample of the **brand new** Security DevNet Express content available to you, your customers, and your partners.  This module will introduce you to some simple ways we can use automation to manage, deploy, and monitor SSE and SASE solutions.  You will be using **two** resources for these exercises, the DevNet Express 2.0 learning environment and a SASE v2 dCloud Lab.

<img width="1420" alt="DNE" src="https://user-images.githubusercontent.com/10421515/185941156-3632b79c-24fb-4e08-903d-617d8400bd04.png">

## Accessing Your SASE Environment

1. Access your Lab Environment here: 
> Use an incognito or private window to access the lab environment!
> https://dcloud.cisco.com/expo/16r4tlz2xklhv16lxp5ue0lu1

## Your DevNet Learning Lab 2.0 Environment

The learning environment uses containers and doesn't require a dedicated development environment as we did for DevNet Express 1.0 and 1.1.

<img width="1420" alt="Interface" src="https://user-images.githubusercontent.com/10421515/185941577-b6b1b9af-b9a9-4265-9ac3-0fd17a16cbd0.png">

You will be using the IDE to write your code and the terminal below will execute the Python scripts.

If you get stuck, need a hint, or just want to jump to the answer, all of the solutions are posted as part of the environment in `/src/solutions/sase` folder.

<img width="705" alt="solutions" src="https://user-images.githubusercontent.com/10421515/185953534-ffd030c9-3a18-44da-b74e-9e5cb33758b1.png">

You will be using the IDE to write your code and the terminal below will execute the Python scripts.

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
duo_integration_key = 'YOUR KEY'
duo_secret_key = 'YOUR SECRET KEY'
duo_api_host = env.DUO_API_HOST
```
You will accomplish the following items at the conclusion of the module:

* Writing a python script that programmatically adds a new user 'granite' to the Duo Users.
* Disables the 'granite' user using the API.

## Umbrella Network Tunnels




