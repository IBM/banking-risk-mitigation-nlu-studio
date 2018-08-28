## Work in Progress
# Banking Risk Mitigation using NLU Studio

## Included Components

* [Watson Natural Language Understanding](https://console.bluemix.net/catalog/services/natural-language-understanding): An IBM Cloud service that can analyze text to extract meta-data from content such as concepts, entities, keywords, categories, sentiment, emotion, relations, semantic roles, using natural language understanding.

## Featured Technologies

* [Natural Language Processing](https://www.ibm.com/watson/services/natural-language-understanding): Natural Language Processing is a field that covers computer understanding and manipulation of human language, and it’s ripe with possibilities for newsgathering.
* [Cloud](https://www.ibm.com/developerworks/learn/cloud/): Accessing computer and information technology resources through the Internet.
* [Python](https://www.python.org/): Python is a programming language that lets you work more quickly and integrate your systems more effectively.

# Deploy to IBM Cloud

Create an [IBM Cloud account](https://console.bluemix.net/registration/?target=%2Fdashboard%2Fapps) and directly deploy the application using the button bellow.

<!--- [![Deploy to IBM Cloud](https://bluemix.net/deploy/button.png)](https://bluemix.net/deploy?repository=https://github.com/IBM/banking-risk-mitigation-nlu-studio) -->


# Watch the Video


## Prerequisite
* [Python](https://www.python.org/downloads/)
* [Git](https://git-scm.com/downloads)
* [IBM Cloud account](https://console.bluemix.net/registration/?target=%2Fdashboard%2Fapps)
* [IBM Cloud CLI](https://console.bluemix.net/docs/cli)

## Steps
1. [Clone the repo](#1-clone-the-repo)
2. [Create IBM Cloud service](#2-create-ibm-cloud-service)
3. [Update the NLU service credentials](#3-update-the-NLU-service-credentials)
4. [Configure Manifest file](#4-configure-manifest-file)
5. [Configure .env file](#5-configure-env-file)
6. [Run Application](#6-run-application)

## 1. Clone the repo

Now you're ready to start working with the app. Clone the repo and change to the directory where the sample app is located.
  ```
git clone https://github.com/IBM/banking-risk-mitigation-nlu-studio
cd banking-risk-mitigation-nlu-studio
  ```

  Peruse the files in the *get-started-python* directory to familiarize yourself with the contents.
  
## 2. Create IBM Cloud service

Create the following IBM Cloud service. Select the appropriate region, organization and space:

  * [**Watson Natural Language Understanding**](https://console.bluemix.net/catalog/services/natural-language-understanding)

  ![](doc/source/images/NLU_Service_instance.png)
  
## 3. Update the NLU service credentials

Open the Watson Natural Language Understanding service in your [IBM Cloud Dashboard](https://console.bluemix.net/dashboard/services) and click on your Natural Language Understanding service.

Once the service is open click the `Service Credentials` menu on the left.

![](doc/source/images/service_credentials.png)

In the `Service Credentials` that opens up in the UI, select whichever `Credentials` you would like to use in the notebook from the `KEY NAME` column. Click `View credentials` and copy `username` and `password` key values that appear on the UI in JSON format.

![](doc/source/images/copy_credentials.png)

Update the `username` and `password` key values in the cell below `2.1 Add your service credentials from IBM Cloud for the Watson services` section.
