# ibm-smart-procurement-advisor

**Headline: IBM Smart Procurement Advisor for SAP ARIBA**

**By: Tushar Trivedi & Ankit Guria**

**How to use IBM Watson Assistant with SAP**

IBM Watson Assistant is an AI-powered virtual agent that provides customers with fast, consistent, and accurate answers across any messaging platform, application, device, or channel. Using AI and natural language processing, Watson Assistant learns from customer conversations, improving its ability to resolve issues starting from the first time while removing the frustration of long wait times, tedious searches, and unhelpful chatbots. With Watson Assistant, you can build conversational interfaces into any application, device, or channel.

As shown in SAP’s Discover Center, SAP Conversational AI is scheduled to be removed from the list of Eligible Cloud Services as of 31.07.2023. (Source: https://discovery-center.cloud.sap/serviceCatalog/conversational-ai?region=all&tab=service_plan)

In this blog, we like to give a short overview how to use IBM Watson Assistant in conjunction with SAP Systems (S/4HANA, Ariba, …)

**Introduction**

**Built with IBM’s Watson AI**

Built in conjunction, this blog talks about the partnership between IBM Watson AI’s conversational power and support  of SAP’s powerful S4 HANA.

In a present day scenario, client-interfacing chatbots integrated with SAP backend systems are used by businesses. As a self-taught developer and architect with IBM I enjoy building simple prototypes for my clients and the developer community to show the basic principles (see below example) of chatbots and similar use-cases. Most chatbots currently leverage IBM Cloud and consist of:
•	Run-time for the application logic like Node.js, Cloud Functions (IBM’s serverless computing platform) or the low-coding platform Node-RED,
•	AI services (Natural Language Processing), and 
•	A frontend (Node-RED, Vue.js, chat platforms).

For developers there’s a lot of content available to get started with IBM Cloud (e.g. on IBM Developer), but in this post I want to describe a hybrid SAP/IBM chatbot scenario, which can help developers integrate both worlds and perhaps even an inspiration for a side hustle.

**What are we building?**

Today, every organisation is working to minimize human efforts and maximize data accuracy. As strategic partners, IBM and SAP are working toward this very automation. SAP ARIBA is one of the most widely used software application for procurement. Creation of a procurement request requires more than 32 fields to be filled. This is an extremely cumbersome activity for the end-user of the SAP ARIBA system, especially for an infrequent user. We came up with a solution where the user will be able to navigate easily due to limited fields and a user-friendly UI. 

**Pre-requisite**

**	Application development –**
Microsoft Visual Studio Code / SAP Business Application Studio / SAP WebIDE
SAP ECC ERP / S4HANA
Intelligent Robotic Process Automation Cloud Studio
SAP ARIBA


**	Watson Assistant Build –**
IBM Watson AI Services (Watson Assistant & Watson Discovery)


**Application Architecture**

<img width="355" alt="image" src="https://media.github.ibm.com/user/406585/files/1a960469-0672-474d-b7a4-a09a6218eeea">


**IBM Watson Assistant Development for the Smart Procurement Chatbot**

First, log into IBM Cloud (https://cloud.ibm.com/login). Once logged into IBM Cloud, you will see the landing page, which should look similar as below:

<img width="357" alt="image" src="https://media.github.ibm.com/user/406585/files/8c3d826d-0889-4a2a-9410-ce6cb5721ccc">

 
Search for “Watson Assistant” in the top search bar and click Watson Assistant under Catalog Results, as shown below. Open Watson Assistant.

<img width="342" alt="image" src="https://media.github.ibm.com/user/406585/files/2f3d4954-5b84-4538-b780-b75cc377acc3">

Click on **Launch Watson Assistant**

<img width="357" alt="image" src="https://media.github.ibm.com/user/406585/files/44eaada9-b16e-491b-96e1-eb8b1e9032c4">

Create assistant by providing below details such as **Assistant name, Description, etc**.

<img width="356" alt="image" src="https://media.github.ibm.com/user/406585/files/ad179afc-3a20-40a7-9fec-d5c5bd89768d">

Click on **Create a new action** button as below and start creating a set of questions which can be asked to the chatbot.

 ![image](https://media.github.ibm.com/user/406585/files/358ebd32-e71c-4166-9293-b3cb24c98abc)
 
Please follow questions with possible answers and the further set of actions or questions which can be asked by a user. 

<img width="357" alt="image" src="https://media.github.ibm.com/user/406585/files/6a6fcc9a-9b52-4628-9620-82a2ffc6f44c">

<img width="357" alt="image" src="https://media.github.ibm.com/user/406585/files/f0c7e9ab-b443-452d-9c1b-3b6d4da2d597">

Click on **Preview** to test the virtual assistant. The below screen will be appear and you will be able to check the queries and questions through the virtual assistant.

<img width="357" alt="image" src="https://media.github.ibm.com/user/406585/files/a2b66b4a-5b32-4d8f-aca8-7e119336501a">

After successful testing, publish the application using Publish button   on the left. Provide the version description and click on Publish.

<img width="357" alt="image" src="https://media.github.ibm.com/user/406585/files/91af3b64-470f-44bb-a84e-f35f1ae54052">

After successful completion of publishing the page, you will be able to see your application Live as below.

<img width="356" alt="image" src="https://media.github.ibm.com/user/406585/files/26f9305b-b576-47bb-b53d-bf26dfea069b">

**Embedding to the UI section:**

We now need to implement the chatbot into the UI. For that, we need to go to the “index.html” and implement the chatbot script into the UI.

<img width="357" alt="image" src="https://media.github.ibm.com/user/406585/files/f3884a9d-a29e-443b-a6f4-15e6bc5bb9bf">

**Application development using IDE (Integrated Development Environment):**
 
As this chatbot is going to be provisioned on a SAP environment development, it is recommended to use SAP Business Application Studio or SAP WebIDE. Here, in this case, we have used Microsoft Visual Studio Code.
 
**Step 1:** 

The initial steps are as follows:
I am using Visual Studio Code in this blog and however it is recommended to use **SAP Business Application Studio**.

Create New SAPUI5 Application
 ![image](https://media.github.ibm.com/user/406585/files/202b5a4d-4ad7-4970-8603-0c52d69008e6)
 
After the project is created, navigate to _Project name > webapp_.

All the respective views are created and the respective controller.js files and the fragments and dialogs are created.

If we have the project built already, we can directly open the folder from our local device.

 ![image](https://media.github.ibm.com/user/406585/files/d5778963-53f9-40d2-9fe6-5331d35c3a20)

**Step 2 (Optional for SAP Business Application Studio) :** 

This step is optional. If you are using SAP Business Application Studio, then you can skip this part and move on to the next step. 
However for Visual studio code, installing of the following extensions and dependencies is required to make the SAP UI5 application ready to execute. (1) NPM, (2) SAP Fiori Tools-Application Modeller, (3) SAP Fiori Tools- Extension Pack and (4) UI5 Tools

 ![image](https://media.github.ibm.com/user/406585/files/5ad6fd5f-413b-47f6-b892-984bd930c240)
 
**Step 3:** 

Then comes the part of setting the manifest.json / yaml file to the destinations.  For that, navigate to webapp>manifest.json or webapp>manifest.yaml as per the nature of the created application.

 ![image](https://media.github.ibm.com/user/406585/files/e704a28d-612e-4b10-8dd7-aa006536edb2)

**Step 4:**

The models and component.js have been set as per the requirements of the development of the web application.

 ![image](https://media.github.ibm.com/user/406585/files/a34e158a-9791-4d60-a8ce-383a0b658417)
 
**Step 5:** 

Navigation between views / webpages is required in our application. **Note: Different ways by different developers, Frontend is vast, isn’t it.**

Adding navTo or router functionalities to the application for the different web pages.
Fig: A small “doNavigate” function snippet.

 ![image](https://media.github.ibm.com/user/406585/files/a1472ab9-403d-4f46-b616-e44fedb31a8e)

**Step 6:**

Complete writing the code for the development of the entire application. The final step is to run the application.
For that, we have already installed the node package manager in step 2 of this section.
We can directly open the directory in the “terminal”>> “New Terminal” option of the VS code.
And run the following command:

Command “npm start” which will open in the browser and redirect it to “http://localhost:8080” and test the application.

 ![image](https://media.github.ibm.com/user/406585/files/c36fbfcf-1747-48a0-bed3-53847d2b2fd9)

Please find the url as mentioned that the following web application is running on the local browser. Thanks to the NPM dependencies, we did in our Step 2.

If we are facing issues while running the application, Follow the steps as mentioned in the steps of Step 2 and then,

Command Pallete> New Terminal> cd projectName
$ npm start

And the following above snippet will execute the application on the local host, maybe 8080.
8080 is the default sandbox port address for Visual Studio Code.

 ![image](https://media.github.ibm.com/user/406585/files/9b2242f3-1a74-49a3-bc56-80bbe260c7fc)


**Step 7:**
Embedding the Watson Assistant Chatbot into the web application:

This following code snippet is already available in the Embed step. Click on the Embed section and copy the code.

The following copied code will be pasted on the webapp>index.html file:

<img width="452" alt="image" src="https://media.github.ibm.com/user/406585/files/49b3bbc3-9724-4aee-a8d1-e84c360b18eb">

**Step 8:**
After successful testing of the web app, we can push it to our repository.

**Output and Process (Testing the scenarios)**

The home page of an application will be available as below. Users will be able to access different functionalities such as manual order historic data, automated orders created through Watson assistant, pinned items of users, orders awaiting for approvals, and orders which are declined. In addition, users will be able to see recent order details on the home page itself. 

<img width="342" alt="image" src="https://media.github.ibm.com/user/406585/files/937edb9d-4743-47ad-8857-cd3ec1036045">

There is an option to use a chatbot which is displayed on the right bottom corner of the application. The user will be able to use all the common functionalities such as placing an order, cancelling an order, check the order status, and all other common queries.

**Orders page:**

Users will be able to get the historic details from the “Orders” tile available on the home page. Users need to click on an order to get the details of a particular order.

<img width="395" alt="image" src="https://media.github.ibm.com/user/406585/files/4829a42e-68f1-49c2-9d9c-35799b9473a4">

**Pinned items page:**

<img width="342" alt="image" src="https://media.github.ibm.com/user/406585/files/3e4ace28-db8f-46b9-8a49-23c6798cb214">
 
**Voice search page:**

Click on the “Microphone” button on the home page and ask for whatever you are looking for. For example, “iPhone” will give us result as below: Watson Speech to Text in action.

<img width="342" alt="image" src="https://media.github.ibm.com/user/406585/files/b43b4728-ff13-4d2d-8579-ee7bf177b5e9">

**Watson Assistant Chatbot in action:**

<img width="375" alt="image" src="https://media.github.ibm.com/user/406585/files/6d23952c-7ed8-4a62-b440-9e13ec9d9ec2">

<img width="182" alt="image" src="https://media.github.ibm.com/user/406585/files/44fb759a-53f5-4c56-89bd-51b079814141">

On one click on the click here - hyperlink, it will redirect to the same UI Catalog on the same screen.

**Unlocking the potential of IBM LLM – IBM WatsonX**

IBM WatsonX is an influential platform for AI and data that possesses the capability to enhance the effectiveness of AI for businesses. It consists of three primary elements: WatsonX.data, WatsonX.ai, and WatsonX.governance. Within our specific scenario, we will illustrate the application of IBM WatsonX in developing an AI chatbot.

We have integrated WatsonX with IBM Smart Procurement Advisor for SAP ARIBA, just as we did before. We will now try to find a pump, but we will not be able to find one. We will receive an information message stating that no results were found and that we should initiate an order via Watson Chat Bot. We will then use Watson Assistant to do so.

<img width="375" alt="image" src="https://media.github.ibm.com/user/406585/files/e6c6338b-cecb-460d-9f41-3815b2d0f838">

Watson Assistant will ask us a few questions to gather the information needed to create a Purchase Requisition. We will need to answer these questions, and Watson Assistant will then create the Purchase Requisition for us.

<img width="172" alt="image" src="https://media.github.ibm.com/user/406585/files/300a96d7-e9a5-4f46-8c2a-5ab120f75da4">

We will only ask for the minimum amount of information from users to create a purchase requisition. Additionally, the system will provide value suggestions to help users fill out the details, making it easier for them to complete the process.

<img width="172" alt="image" src="https://media.github.ibm.com/user/406585/files/ca6ecb8a-c24a-45e6-bbc2-90599a92aff8">

The system will generate a summary of the purchase requisition, allowing users to verify all of the details.

<img width="172" alt="image" src="https://media.github.ibm.com/user/406585/files/972f59fb-4bb3-4ec6-99ac-807ee4eba8e2">

Hence, to create a purchase requisition, Watson Assistant will ask us a few questions and provide value suggestions. It will then generate a summary of the requisition for us to verify.

**SAP Intelligent RPA (Robotic Process Automation)**

The details from SAP UI5 application or from Watson Assistant will be passed to the SAP backend. They will be sent in a XML format to the SAP standard interface using OData interface and further data will be sent to Automation Workflow for creation of the Purchase Order. I have mentioned the possible business scenarios:
1.	SAP ECC and SAP ARIBA: The data from SAP UI5 or Watson Assistant to OData for single or multiple Purchase Order(s) will be created using SAP RPA automation workflow in SAP ECC and SAP ARIBA both. This workflow will be designed and developed using Intelligent Robotic Automation Cloud Studio.
2.	SAP ECC Only: The data will flow from SAP UI5 or Watson Assistant to OData and a single or multiple Purchase Order(s) will be created using SAP RPA automation workflow in SAP ECC. This workflow will be designed and developed using Intelligent Robotic Automation Cloud Studio.
3.	SAP ARIBA Only: The data will flow from SAP UI5 or Watson Assistant to OData and the Purchase Order will be created in the SAP ARIBA system where SAP RPA automation workflow will create a single or multiple Purchase Order(s) in SAP ARIBA. This workflow will be designed and developed using Intelligent Robotic Automation Cloud Studio.

**Conclusion:**

Leveraging the IBM smart Machine Learning algorithm, Natural Learning Processing (NLP), along with smart and wide application development of the SAP development toolkit, has enabled “IBM Smart Procurement Advisor for SAP Ariba” come to life.
The IBM Watson Assistant chatbot widget can be added to the UI. The IBM Watson Assistant has a lot more of features that can be used. 
Thank you for reading!
Feel free to leave your feedback, suggestions, and questions! 
You can find more about this Assistant : 

Built with Watson AI. 
