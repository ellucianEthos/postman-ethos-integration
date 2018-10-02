# Ethos Integration Postman Examples

Postman is an API Development Environment that allows for the development and testing of APIs, like those in Ethos Integration. Postman is a free and cross-platform application.  Get Postman here -> https://www.getpostman.com

This repository contains a Postman *collection* and *environment*. A *collection* is simply a group of related API requests. The collection here contains examples of how to do things in Ethos Integration like obtaining an access token, calling GET/POST/PUT/DEL on a resource and consuming change-requests. An *environment* is a set of key-value pairs, essentially variables, that can be shared among API requests. The environment in this repository is used to store an API key and JWT access token.

For more Postman learning and documentation start here -> https://learning.getpostman.com/concepts/

## Getting Started

Clone or download the repository to your machine. The collection and environment files are in json format. Launch Postman and import the collection json file by clicking the **Import** button at the top of the Postman application.

![](/screenshots/postman1.png)

You will see the collection loaded into the collections browser on the left. The collection format version is v2.1, older versions of Postman may not be able to import the file and you must update Postman.

![](/screenshots/postman2.png)

Next import the environment json file by clicking the gear icon (Manage Environments) in the upper right and click **Import**.

![](/screenshots/postman3.png)

Now that the collection and environment are loaded into Postman, enter your API Key into the environment variable. Click the gear icon (Manage Environments) again and click on the "Ethos Integration" environment.  Update the variable "API Key" with a valid API Key value and click **Update**.

![](/screenshots/postman4.png)

Finish the setup by selecting the environment from the dropdown menu so that Postman will use it.

![](/screenshots/postman5.png)

## More Detail

The general process for using Ethos Integration APIs is:
* Use API Key to obtain JWT Access token
* Use JWT Access Token to make API calls

The JWT Access token expires after 5 minutes, so it is not necessary to obtain a new one *every* time an API call is made. If an expired JWT Access Token is used to make an API call the HTTP response will be **401 Unauthorized**.

In this Postman *collection* and *environment* the API Key and JWT Access Token are stored in environment variables and the API requests will use them. If you examine the API call "Use API Key to get Access Token" you will see that Postman uses the API Key stored in the environment variable and then stores the result the "Access Token" environment variable.

![](/screenshots/postman6.png)

Subsequent API calls will then use the value stored in "Access Token" for authorization. If an API call returns a **401 Unauthorized** simply click on the "Use API Key to get Access Token" request again to obtain a new JWT Access Token.


This document was written using Postman v6.3.0.
