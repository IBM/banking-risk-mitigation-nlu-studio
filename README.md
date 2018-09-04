## WORK IN PROGRESS
# Banking Risk Mitigation using NLU Studio

Knowing your Client is an essential best practice because it acts as a basis to decide whether or not to invest in a particular client. To be successful in taking the right decision, you must operate on pertinent, accurate, and timely information. The information you gather and the relationships you establish are critical for an organization investing in a numerous number of client. A poorly planned and executed initial call could limit your opportunity for future business. 

But how can we gather information to take the right decisions?

We can ask questions about the company’s products and services, customers, suppliers, facilities, management, ownership, and history. This is when you can develop your initial observations about management’s behavior and start to evaluate their qualifications and abilities to carry out the company’s business strategy. On subsequent calls, investigate competition, market share, and the probable impact of economic conditions on the business. And identify the company’s business strategy and what the company must do to succeed.

What if we can build a tool that can help you gather all the required information about your clients. To help you take an informed decision to whether or not to invest in a client?

This pattern provides real-time information regarding a client, known as a client-network, all collated in a single place. This information is in compliance to the most important events impacting any organization. The following are the event triggers in the built application: 

* Management Change
* Management Default
* Credit Rating
* Strike
* Share Price Deviation

This code pattern takes real-time information from popular news sites, extracts the clients affected by it with the help of [Watson Natural Language Understanding](https://console.bluemix.net/catalog/services/natural-language-understanding). This is achieved with the help of the following code patterns:
* [Augmented Classification of text with Watson Natural Language Understanding and IBM Data Science experience](https://developer.ibm.com/code/patterns/extend-watson-text-classification)
* [Correlation of text content across documents using Watson Natural Language Understanding, Python NLTK and IBM Data Science experience](https://developer.ibm.com/code/patterns/watson-document-correlation/)

Finally, a flask application connects the algorithm to a UI which can be used by a user to prune down to the required information.

![](doc/source/images/architecture.png)

## Flow

1. The user interacts with the app UI to request relevant information corresponding to an event or a client
2. The web app UI interacts with the Python-Flask server to receive the required information from the appropriate api.
3. The flask apis scrape real-time news from popular online news portals. 
4. The scraped data is sent to NLU Studio to extract important entities. 
5. A configuration json file is sent into the flask app, to further prune on the results obtained on NLU.
6. Finally, all the collected information is pushed back into the interactive UI.


## Included Components

* [Watson Natural Language Understanding](https://console.bluemix.net/catalog/services/natural-language-understanding): An IBM Cloud service that can analyze text to extract meta-data from content such as concepts, entities, keywords, categories, sentiment, emotion, relations, semantic roles, using natural language understanding.

## Featured Technologies

* [Natural Language Processing](https://www.ibm.com/watson/services/natural-language-understanding): Natural Language Processing is a field that covers computer understanding and manipulation of human language, and it’s ripe with possibilities for newsgathering.
* [Cloud](https://www.ibm.com/developerworks/learn/cloud/): Accessing computer and information technology resources through the Internet.
* [Python](https://www.python.org/): Python is a programming language that lets you work more quickly and integrate your systems more effectively.
* [Artificial Intelligence](https://www.ibm.com/services/artificial-intelligence): Artificial intelligence is intelligence demonstrated by machines, in contrast to the natural intelligence displayed by humans and other animals.

# Watch the Video

Insert Video

## Prerequisite
* [Python](https://www.python.org/downloads/)
* [Git](https://git-scm.com/downloads)
* [IBM Cloud account](https://console.bluemix.net/registration/?target=%2Fdashboard%2Fapps)
* [IBM Cloud CLI](https://console.bluemix.net/docs/cli)

There are three ways to run the application, depending on your need you may choose to run in any one of the following ways:
* [Deploy to IBM Cloud](#deploy-to-ibm-cloud): This will directly clone this git repo as is and run on your IBM Cloud Foundry Organisation.
* [Run Application on IBM Cloud](#run-application-on-ibm-cloud): This will let you make the desired changed in the code and then push the application onto your IBM Cloud Foundry Organisation.
* [Run Application locally](#run-application-locally): This will show you how to run the application localhost, using the provided Flask Server

# Deploy to IBM Cloud

Create an [IBM Cloud account](https://console.bluemix.net/registration/?target=%2Fdashboard%2Fapps) and directly deploy the application using the button below.

[![Deploy to IBM Cloud](https://bluemix.net/deploy/button.png)](https://bluemix.net/deploy?repository=https://github.com/IBM/banking-risk-mitigation-nlu-studio)


# Run Application on IBM Cloud


## Steps
1. [Clone the repo](#1-clone-the-repo)
2. [Create IBM Cloud service](#2-create-ibm-cloud-service)
3. [Run the Application on IBM Cloud](#3-run-the-application-on-ibm-cloud)
4. [Troubleshooting](#4-troubleshooting)

## 1. Clone the repo

Now you're ready to start working with the app. Clone the repo and change to the directory where the sample app is located.
  ```
git clone https://github.com/IBM/banking-risk-mitigation-nlu-studio
cd banking-risk-mitigation-nlu-studio
  ```
  
## 2. Create IBM Cloud service

Create the following IBM Cloud service. Name the service `Bankingriskmitigation`. Select your desired region, organization and space:

  * [**Watson Natural Language Understanding**](https://console.bluemix.net/catalog/services/natural-language-understanding)

  ![](doc/source/images/NLU_Service_instance.png)
  
  If you wish to change the name of your NLU service instance, be sure to update the service name in `manifest.yml`.
  

## 3. Run the Application on IBM Cloud

You can push the app to IBM Cloud using [IBM Cloud CLI](https://console.bluemix.net/docs/cli). This will use the services and application name in the `manifest.yml` file.  From your root directory login into IBM Cloud using CLI:
```
ibmcloud login
```
And push the app to IBM Cloud:
```
ibmcloud cf push Client_Network_Banking_V1
```

If you wish to change the name of the IBM Cloud application- Navigate to the `manifest.yml` file and update the `name` field.

## 4. Troubleshooting

* To troubleshoot your IBM Cloud application, use the logs. To see the logs, run:

```bash
ibmcloud cf logs Client_Network_Banking_V1 --recent
```

# Run Application locally

Follow Steps 1-3 from the previous section.

Install the dependencies listed in the [requirements.txt](https://pip.readthedocs.io/en/stable/user_guide/#requirements-files) file to be able to run the app locally.

You can optionally use a [virtual environment](https://packaging.python.org/installing/#creating-and-using-virtual-environments) to avoid having these dependencies clash with those of other Python projects or your operating system.
  ```
pip install -r requirements.txt
  ```

Run the app.
  ```
python app.py
  ```

View your app at: http://localhost:8000




# License

[Apache 2.0](LICENSE)


