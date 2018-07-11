![](https://github.com/Microsoft/MCW-Template-Cloud-Workshop/raw/master/Media/ms-cloud-workshop.png "Microsoft Cloud Workshops")


<div class="MCWHeader1">
Mobile app innovation
</div>

<div class="MCWHeader2">
Whiteboard design session student guide
</div>

<div class="MCWHeader3">
June 2018
</div>

Information in this document, including URL and other Internet Web site references, is subject to change without notice. Unless otherwise noted, the example companies, organizations, products, domain names, e-mail addresses, logos, people, places, and events depicted herein are fictitious, and no association with any real company, organization, product, domain name, e-mail address, logo, person, place or event is intended or should be inferred. Complying with all applicable copyright laws is the responsibility of the user. Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.

Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.

The names of manufacturers, products, or URLs are provided for informational purposes only and Microsoft makes no representations and warranties, either expressed, implied, or statutory, regarding these manufacturers or the use of the products with any Microsoft technologies. The inclusion of a manufacturer or product does not imply endorsement of Microsoft of the manufacturer or product. Links may be provided to third party sites. Such sites are not under the control of Microsoft and Microsoft is not responsible for the contents of any linked site or any link contained in a linked site, or any changes or updates to such sites. Microsoft is not responsible for webcasting or any other form of transmission received from any linked site. Microsoft is providing these links to you only as a convenience, and the inclusion of any link does not imply endorsement of Microsoft of the site or the products contained therein.
© 2018 Microsoft Corporation. All rights reserved.

Microsoft and the trademarks listed at https://www.microsoft.com/en-us/legal/intellectualproperty/Trademarks/Usage/General.aspx are trademarks of the Microsoft group of companies. All other trademarks are property of their respective owners.

**Contents**

<!-- TOC -->

- [Mobile app innovation whiteboard design session student guide](#mobile-app-innovation-whiteboard-design-session-student-guide)
    - [Abstract and learning objectives](#abstract-and-learning-objectives)
    - [Step 1: Review the customer case study](#step-1-review-the-customer-case-study)
        - [Customer situation](#customer-situation)
        - [Customer needs](#customer-needs)
        - [Customer objections](#customer-objections)
        - [Infographic of common scenarios](#infographic-of-common-scenarios)
    - [Step 2: Design a proof of concept solution](#step-2-design-a-proof-of-concept-solution)
    - [Step 3: Present the solution](#step-3-present-the-solution)
    - [Wrap-up](#wrap-up)
    - [Additional references](#additional-references)

<!-- /TOC -->

# Mobile app innovation whiteboard design session student guide


## Abstract and learning objectives

This package is designed to guide attendees through an implementation of an end-to-end mobile baggage tracking system for a customer in the airline industry. Attendees will design an IoT solution simulating data emitted from RFID tags attached to airline passengers' checked luggage, and mobile applications to allow employees and customers to track those bags from any device. Upon completion of the session, attendees will better understand how to:

-   Set up an IoT Hub, and register RFID devices

-   Consider the steps required to migrate legacy systems to the Azure platform

-   Connect on-premises applications to Azure using PowerApps Data Gateway

-   Use Azure Functions to send and receive data from Cosmos DB

-   Configure VSTS CI/CD pipelines

## Step 1: Review the customer case study 

**Outcome** 

Analyze your customer’s needs.

Timeframe: 15 minutes

Directions: With all participants in the session, the facilitator/SME presents an overview of the customer case study along with technical tips. 

1.  Meet your table participants and trainer 
2.  Read all of the directions for steps 1–3 in the student guide 
3.  As a table team, review the following customer case study

### Customer situation

Contoso Air, founded in 1932, is a leader in the air travel industry, with service to more than 70 different countries/regions around the globe. Contoso is currently modernizing their entire ticketing and operations platform. With a global workforce in over 70 countries/regions, there is a need to access data with extremely low latency thus requiring replication across geographical regions. Furthermore, employees are becoming increasingly mobile and digital savvy. They expect to be able to have access to their data in real time from any type of the common mobile platforms: be it UWP, iOS, or Android. Contoso's competitors are smaller and nimbler, as such they have been able to transform digitally much faster and provide employees and customers with a better experience.

Over time, Contoso hopes to be able to shift to a 100% cloud infrastructure, but they have an extensive number of on-premises legacy systems which are extremely costly to upgrade. They are interested in using Azure to help securely expose specific information housed in those legacy systems accessible to other applications. This will also enable their global workforce to tailor their own application experiences in order to perform their jobs accurately and effectively. For this, they will require both a broadly available, highly scalable cloud that also offers hybrid capabilities to bridge to their on-premises infrastructure.

Contoso has already recently migrated email, file sharing, collaboration, chat, and VoIP systems into the cloud by taking advantage of the services provided in Office 365. As such, they have already set up federated AD, as well as other Microsoft 365 services (including the Microsoft Graph) which are all available for integration. They have various resources spread across three Azure regions.

To remain competitive and improve their customer satisfaction ratings, Contoso Air wishes to modernize their baggage handling and tracking process. This includes the introduction of RFID luggage tags, equipping baggage handlers with mobile devices to perform luggage scans, a customer luggage tracking mobile application, and adding IoT enabled RFID antennas and scanners throughout the baggage handling process. Employees and customers alike will be able to track the exact position of a piece of luggage from the time that it leaves its owner's hands to the time that it returns to them at the baggage claim.

At any given time, Contoso has an average of 120 active flights on the ground (processing baggage) at 60 locations worldwide. Each flight has an estimated 180 customers with an average of 360 checked bags -- it is beneficial that the handling and tracking of these bags is improved.

By implementing this system, Contoso will be able to improve their metrics as it relates to lost luggage. At the same time, they will improve their satisfaction ratings by providing their customers with piece of mind by giving them visibility into exactly where their luggage is at all times. Even if luggage is lost, Contoso Air can start the search at the last known scan location, thus saving time and money.

### Customer needs

1.  Low-latency data replication across geographical regions

2.  Client applications for web, iOS, Android, and UWP

3.  Real-time location data for baggage

4.  RFID labels, antennas, scanners, and employee mobile application

5.  The ability to quickly innovate on new mobile application features with high quality

-   Automated Build, Test, and Deployment

-   Crash/Analytics

-   cDashboarding

### Customer objections

1.  Contoso Air is worried about potential security-related disruptions to the system

2.  There is concern over Azure's ability to communicate reliably with IoT RFID scanners

3.  Is Xamarin the right solution for the customer mobile applications?

4.  How does this solution guarantee low data latency?

5.  There will be thousands of scanners being used at a given time, does this solution scale?

6.  The new system may require querying data from on-premises data sources, how do you bridge that gap?

### Infographic of common scenarios 

![This data flow diagram illustrates how Microsoft Azure services like IoT Hub, Data Lake, and SQL Data Warehouse enable 'big data' solutions that can the handle high velocity data that is typical of IoT. Components in this diagram interact with each other between end users and the enterprise, and the components are organized in eight groups that flow in the following order: On Premises, Ingest, Stream Processing, Batch Storage, Speed Serving, Batch Processing, Batch View Serving, and Analytics Clients. At this time, we are unable to capture all of the information in the window. Future versions of this course should address this.](images/WhiteboardDesignSessionTrainerGuide-Mobileappinnovationimages/media/image2.png "Common Internet of Things (IoT) scenarios infographic")

## Step 2: Design a proof of concept solution

**Outcome** 

Design a solution and prepare to present the solution to the target customer audience in a 15-minute chalk-talk format. 

Timeframe: 60 minutes

**Business needs**

Directions: With all participants at your table, answer the following questions and list the answers on a flip chart.

1.  Who should you present this solution to? Who is your target customer audience? Who are the decision makers? 
2.  What customer business needs do you need to address with your solution?

**Design** 
Directions: With all participants at your table, respond to the following questions on a flip chart.

*High-level architecture*

1.  Without getting into the details (the following sections will address the particular details), diagram your initial vision for handling the top-level requirements for data security, ingestion, processing, and exposure to the mobile applications. You will refine this diagram as you proceed.

*Data Security*

1.  Given their existing services, how would you ensure that all communication to and from the system is secured?

    -   How would you authenticate and authorize an RFID scanner client?

    -   How would you authenticate and authorize an employee using a client application?

    -   How would you authenticate and authorize a customer using a mobile application?

2.  How would you ensure that in-transit data is secured?

*Data Ingestion*

1.  What format would you choose for the messages being ingested by the system?

2.  Define the messages that need to be ingested:

    -   Define the structure of the message sent from an employee checking in a bag for a customer

    -   Define the structure of the message sent form the RFID scanners

    -   Define the structure of the message sent from the baggage handler loading a bag into the plane

    -   Define the structure of the message sent from the baggage handler, indicating that the last bag has been loaded into the plane

    -   Define the structure of the message sent from the baggage handler unloading a bag from the plane

    -   Define the structure of the message sent from the baggage handler, indicating that the last bag has been unloaded from the plane

3.  What is the anticipated volume in messages expected from the RFID IoT solution that Contoso Air will need to support given their employee and customer base?

4.  How would you propose they ingest that quantity of messages? What Azure service would you recommend and why? At what initial scale?

5.  What protocol would they use in sending data to the service(s) used for message ingestion?

6.  Define any endpoint(s) used for message ingestion

*Data Processing*

1.  What Azure service would you use to guarantee ingested data is processed reliably?

2.  How would you ensure that the data is processed with low-latency?

3.  Which Azure service would you use to persist the current state of the RFID luggage tag?

4.  How will you ensure that persisted data is available at low-latency around the globe?

*Data Exposure*

1.  What Azure service would you recommend that will provide read-only luggage information to the Customer mobile application. Why did you make this choice?

2.  What protocol is used when the Customer mobile application initiates communication with the service you decided upon in \#1?

*Client Applications*

1.  Which Azure service do you recommend using for housing application source code?

2.  What Azure services do you recommend for automated builds, testing, and deployment?

3.  Which Azure service would you use to store application secrets, such as certificates or connection strings so that they aren't readily available in client application source control?

4.  How would you bridge data between on-premises systems and Microsoft Azure?

5.  What Azure service would you recommend for Contoso Air business users to be able to self-service a CRUD (Create, Read, Update, Delete) application that can be made available on both web and mobile?

**Prepare**

Directions: With all participants at your table: 

1.  Identify any customer needs that are not addressed with the proposed solution
2.  Identify the benefits of your solution
3.  Determine how you will respond to the customer’s objections

Prepare a 15-minute chalk-talk style presentation to the customer.

## Step 3: Present the solution

**Outcome**
 
Present a solution to the target customer audience in a 15-minute chalk-talk format.

Timeframe: 30 minutes

**Presentation** 

Directions:
1.  Pair with another table
2.  One table is the Microsoft team and the other table is the customer
3.  The Microsoft team presents their proposed solution to the customer
4.  The customer makes one of the objections from the list of objections
5.  The Microsoft team responds to the objection
6.  The customer team gives feedback to the Microsoft team 
7.  Tables switch roles and repeat Steps 2–6

## Wrap-up 

Timeframe: 15 minutes

-   Tables reconvene with the larger group to hear the facilitator/SME share the preferred solution for the case study.

## Additional references
|    |            |
|----------|:-------------:|
| **Description** | **Links** |
| GDPR Compliance | <https://gallery.technet.microsoft.com/How-Azure-Can-Help-788a4979> |
| Azure Key Vault | <https://docs.microsoft.com/en-us/azure/key-vault/key-vault-whatis> |
| PowerApps - Business User self-service web and mobile application creation | <https://docs.microsoft.com/en-us/powerapps/getting-started> |
| PowerApps - Using PowerApps with Azure Functions | <https://blogs.msdn.microsoft.com/srikantan/2017/07/22/using-azure-functions-cosmos-db-and-powerapps-to-build-deploy-and-consume-serverless-apps/> |
| PowerApps Data Gateway | <https://docs.microsoft.com/en-us/powerapps/gateway-reference> |
| PowerApps - Receiving Push Notifications with PowerApps| <https://powerapps.microsoft.com/en-us/blog/add-push-notification-to-you-app-and-boost-usage-and-retention/> |
| Cosmos DB, Azure Functions, PowerApps | <https://blogs.msdn.microsoft.com/srikantan/2017/07/22/using-azure-functions-cosmos-db-and-powerapps-to-build-deploy-and-consume-serverless-apps/> |
| IoT Hub - Routing messages from IoT hub to a queue | <https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-csharp-csharp-process-d2c> |
| IoT Hub - IoT Hub and the MQTT protocol | <https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-mqtt-support> |
| Azure Functions | <https://docs.microsoft.com/en-us/azure/azure-functions/> |
| Azure Active Directory | <https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-integrating-applications> |
| Visual Studio App Center | <https://docs.microsoft.com/en-us/appcenter/> |
| Visual Studio Team Services | <https://docs.microsoft.com/en-us/vsts/> |
| Azure App Service / Xamarin | <https://docs.microsoft.com/en-us/azure/app-service-mobile/app-service-mobile-xamarin-forms-get-started-users> <https://docs.microsoft.com/en-us/azure/app-service-mobile/app-service-mobile-dotnet-backend-how-to-use-server-sdk#how-to-work-with-authentication> |
| Cosmos DB | <https://docs.microsoft.com/en-us/azure/cosmos-db/online-backup-and-restore> |
