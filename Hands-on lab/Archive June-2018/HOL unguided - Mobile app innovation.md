![](https://github.com/Microsoft/MCW-Template-Cloud-Workshop/raw/master/Media/ms-cloud-workshop.png "Microsoft Cloud Workshops")


<div class="MCWHeader1">
Mobile app innovation
</div>

<div class="MCWHeader2">
Hands-on lab unguided
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

- [Abstract and learning objectives](#abstract-and-learning-objectives)
- [Overview](#overview)
- [Solution architecture](#solution-architecture)
- [Requirements](#requirements)
- [Exercise 1: Azure data, storage, and serverless environment setup](#exercise-1-azure-data-storage-and-serverless-environment-setup)
    - [Task 1: Create your project in Azure DevOps](#task-1-create-your-project-in-azure-devops)
        - [Tasks to complete](#tasks-to-complete)
        - [Exit criteria](#exit-criteria)
    - [Task 2: Commit starter project to your Azure DevOps project](#task-2-commit-starter-project-to-your-azure-devops-project)
        - [Tasks to complete](#tasks-to-complete-1)
        - [Exit criteria](#exit-criteria-1)
- [Exercise 2: Configure Visual Studio App Center](#exercise-2-configure-visual-studio-app-center)
    - [Help references](#help-references)
    - [Task 1: Create a new iOS / Xamarin app](#task-1-create-a-new-ios--xamarin-app)
        - [Tasks to complete](#tasks-to-complete-2)
        - [Exit criteria](#exit-criteria-2)
    - [Task 2: Connect iOS app to App Center](#task-2-connect-ios-app-to-app-center)
        - [Tasks to complete](#tasks-to-complete-3)
        - [Exit criteria](#exit-criteria-3)
    - [Task 3: Create a new Android / Xamarin app](#task-3-create-a-new-android--xamarin-app)
        - [Tasks to complete](#tasks-to-complete-4)
        - [Exit criteria](#exit-criteria-4)
    - [Task 4: Connect Xamarin.Android app to App Center](#task-4-connect-xamarinandroid-app-to-app-center)
        - [Tasks to complete](#tasks-to-complete-5)
        - [Exit criteria](#exit-criteria-5)
    - [Task 5: Commit your changes to Azure DevOps](#task-5-commit-your-changes-to-azure-devops)
        - [Tasks to complete](#tasks-to-complete-6)
        - [Exit criteria](#exit-criteria-6)
    - [Task 6: Connect iOS & Android apps in App Center to Azure DevOps and configure/launch build](#task-6-connect-ios--android-apps-in-app-center-to-azure-devops-and-configurelaunch-build)
        - [Tasks to complete](#tasks-to-complete-7)
        - [Exit criteria](#exit-criteria-7)
    - [Task 7: Enable Telemetry (App Insights in App Center)](#task-7-enable-telemetry-app-insights-in-app-center)
        - [Tasks to complete](#tasks-to-complete-8)
        - [Exit criteria](#exit-criteria-8)
- [Exercise 3: Configure Azure Cosmos DB and Azure functions](#exercise-3-configure-azure-cosmos-db-and-azure-functions)
    - [Help references](#help-references-1)
    - [Task 1: Configure your Cosmos DB instance](#task-1-configure-your-cosmos-db-instance)
        - [Tasks to complete](#tasks-to-complete-9)
        - [Exit criteria](#exit-criteria-9)
    - [Task 2: Create collections in your Cosmos DB instance](#task-2-create-collections-in-your-cosmos-db-instance)
        - [Tasks to complete](#tasks-to-complete-10)
        - [Exit criteria](#exit-criteria-10)
    - [Task 3: Create a new Application Insights instance](#task-3-create-a-new-application-insights-instance)
        - [Tasks to complete](#tasks-to-complete-11)
        - [Exit criteria](#exit-criteria-11)
    - [Task 4: Create a new Azure Function App](#task-4-create-a-new-azure-function-app)
        - [Tasks to complete](#tasks-to-complete-12)
        - [Exit criteria](#exit-criteria-12)
    - [Task 5: Connect your function project to Cosmos DB](#task-5-connect-your-function-project-to-cosmos-db)
        - [Tasks to complete](#tasks-to-complete-13)
        - [Exit criteria](#exit-criteria-13)
    - [Task 6: Connect your project to Application Insights](#task-6-connect-your-project-to-application-insights)
        - [Tasks to complete](#tasks-to-complete-14)
        - [Exit criteria](#exit-criteria-14)
    - [Task 7: Add functions to your app](#task-7-add-functions-to-your-app)
        - [Tasks to complete](#tasks-to-complete-15)
        - [Exit criteria](#exit-criteria-15)
    - [Task 8: Deploy your app to Azure](#task-8-deploy-your-app-to-azure)
        - [Tasks to complete](#tasks-to-complete-16)
        - [Exit criteria](#exit-criteria-16)
- [Exercise 4: Setup IoT hub](#exercise-4-setup-iot-hub)
    - [Help references](#help-references-2)
    - [Task 1: Create the IoT hub in Azure](#task-1-create-the-iot-hub-in-azure)
        - [Tasks to complete](#tasks-to-complete-17)
        - [Exit criteria](#exit-criteria-17)
    - [Task 2: Create a device identity](#task-2-create-a-device-identity)
        - [Tasks to complete](#tasks-to-complete-18)
        - [Exit criteria](#exit-criteria-18)
    - [Task 3: Set up the backend keys for the database and Functions](#task-3-set-up-the-backend-keys-for-the-database-and-functions)
        - [Tasks to complete](#tasks-to-complete-19)
        - [Exit criteria](#exit-criteria-19)
    - [Task 4: Set up the program to scan the bags](#task-4-set-up-the-program-to-scan-the-bags)
        - [Tasks to complete](#tasks-to-complete-20)
        - [Exit criteria](#exit-criteria-20)
    - [Task 5: Run the program to scan the bags](#task-5-run-the-program-to-scan-the-bags)
        - [Tasks to complete](#tasks-to-complete-21)
        - [Exit criteria](#exit-criteria-21)
- [Exercise 5: Connect the mobile app to the backend](#exercise-5-connect-the-mobile-app-to-the-backend)
    - [Task 1: Connect app to Azure backend](#task-1-connect-app-to-azure-backend)
        - [Tasks to complete](#tasks-to-complete-22)
        - [Exit criteria](#exit-criteria-22)
    - [Task 2: Create a Fight List page](#task-2-create-a-fight-list-page)
        - [Tasks to complete](#tasks-to-complete-23)
        - [Exit criteria](#exit-criteria-23)
    - [Task 3: Create a Flight List view model](#task-3-create-a-flight-list-view-model)
        - [Tasks to complete](#tasks-to-complete-24)
        - [Exit criteria](#exit-criteria-24)
    - [Task 4: Connect the view model to the page](#task-4-connect-the-view-model-to-the-page)
        - [Tasks to complete](#tasks-to-complete-25)
        - [Exit criteria](#exit-criteria-25)
    - [Task 5: Add Flight List page to the navigation service](#task-5-add-flight-list-page-to-the-navigation-service)
        - [Tasks to complete](#tasks-to-complete-26)
        - [Exit criteria](#exit-criteria-26)
    - [Task 1: Run the app and verify that it successfully retrieves flight data](#task-1-run-the-app-and-verify-that-it-successfully-retrieves-flight-data)
        - [Tasks to complete](#tasks-to-complete-27)
        - [Exit criteria](#exit-criteria-27)
- [After the hands-on lab](#after-the-hands-on-lab)
    - [Task 1: Delete the resource group in which you placed your Azure resources.](#task-1-delete-the-resource-group-in-which-you-placed-your-azure-resources)

<!-- /TOC -->

## Abstract and learning objectives 

In this hands-on lab, you will implement the steps to build an IoT solution for an end-to-end mobile baggage tracking system, that leverages cloud services and cross-platform mobile development.

At the end of this hands-on lab, you will discover how to leverage Azure services to implement an IoT solution that includes, RFID tracking, mobile apps, and a continuous integration pipeline for developers.

## Overview

The Mobile app innovation hands-on lab is an exercise that will challenge you to implement an end-to-end scenario using a supplied sample that is based on Microsoft Azure and related services. The scenario will include implementing IoT Hub, App Center, Application Insights, Azure Functions, and Azure Cosmos DB. The hands-on lab can be implemented on your own, but it is highly recommended to pair up with other members at the workshop to more closely model a real-world experience and to allow each member to share their expertise for the overall solution.

## Solution architecture

Below is a diagram of the solution architecture you will build in this lab. Please study this carefully so you understand the whole of the solution as you are working on the various components.

![Icons that are connected by arrows comprise this diagram, which is divided into three groups: Internal, Cloud, and Public. Azure Active Directory separates the Internal and Cloud groups, and SSL/JWT separates the Cloud and Public groups. At this time, we are unable to capture all of the information in the window. Future versions of this course should address this.](images/Hands-onlabunguided-Mobileappinnovationimages/media/image2.png "Solution architecture diagram")

From a high-level, a customer arrives to the airport with a bag that needs to be checked. The customer is attended to by an employee of Contoso Air with a computer. The employee affixes an RFID tag to the luggage and associates it with the customer and flight information using a PowerApps application. The mobile application triggers this information to be stored in Cosmos DB via an HttpTrigger.

The luggage is then placed on the luggage conveyor belt, where an RFID scanner scans the tag. The RFID scanner utilizes MQTT protocol to send a status message for the luggage to an IoT Hub. The IoT Hub is configured with a Service Bus Queue endpoint and corresponding filter that identifies the status message. Once matched, message is then forwarded to the Service Bus Queue. Having the messages sent to the Service Bus Queue ensures reliability as items will not be removed from the queue until processed. Listening to this queue is an Azure Function, which is then triggered to store the current location of the luggage into Cosmos DB.

The baggage handler then receives the luggage at the plane. As the luggage is loaded onto the plane, each one is scanned using a Xamarin-based mobile application where an Azure function is initiated via an HttpTrigger, and the location of the luggage is updated as having been loaded on the plane. Once all luggage has been loaded onto the plane, the baggage handler application sends another message indicating that all bags are loaded on the plane. This status is also sent along to Cosmos DB via an HttpTrigger. This is a great place to implement notifications for things, such as a bag being loaded onto the wrong plane, or identifying bags that are missing from a flight.

Meanwhile, the customer has boarded the flight, and as the cabin door is shut, they can access their Xamarin-based mobile application. Using information from their luggage receipt, the customer can see that their bag has made it safely on the flight.

Using the same workflow as outlined above, once the flight has landed at its destination, each bag is scanned upon its removal from the plane and its location information is updated. The luggage is then placed on the luggage conveyor belt at baggage claim where RFID scanners will again scan them and update their location. The customer is then able to retrieve their bag from baggage claim.

In the event that a piece of luggage has gone missing, due to the fact that its location is updated often during the baggage handling process, the last known location of the bag will be utilized to begin the search. This system would also identify if a bag may have been inadvertently directed toward an incorrect flight or placed on an incorrect baggage claim conveyor.

## Requirements

1.  Using the same Microsft.com account:

    -   Azure Subscription

    -   Azure DevOps account

    -   Account in Mobile Center

2.  Virtual Machine

    -   Please note, do **NOT** use a VM for this lab. You will not be able to run the simulated mobile app from a virtual machine.

3.  Local machine configured with (**complete the day before the lab!**):

  -   Windows

       -  Workstation with VT-X Support w/Hyper-V Disabled (under Programs and Features in Windows Settings)

       - Intel HAXM Support installed

         Instructions: <https://developer.xamarin.com/guides/android/getting_started/installation/android-emulator/hardware-acceleration/>

       - Windows 10 (Fall Creators Update recommended)

       - Visual Studio 2017 (15.7.4 Required)

   -   Mac

        -  Visual Studio for Mac (latest stable release)

        - Xcode 9.2 (or current latest stable release)

4.  Android SDKs (21, 22, 23, 24, 25, 26, 27)

5.  NET Framework 4.7.1 runtime (or higher)

    -   <https://www.microsoft.com/net/download/windows>

## Exercise 1: Azure data, storage, and serverless environment setup

**Duration**: 15 minutes

A robust DevOps chain is critical in being able to build, deploy, and monitor your app in the wild. This starts with strong source control, and a structured project management solution.

### Task 1: Create your project in Azure DevOps

Create a new project in the Azure DevOps account you created at the start of this lab.

#### Tasks to complete

-   Create a new project named **ContosoBaggage**, and select the **Git** version control option

#### Exit criteria

-   You have a new project in which you can store your source code using git

### Task 2: Commit starter project to your Azure DevOps project

#### Tasks to complete

-   Download the starter code from <http://bit.ly/2F2JQTa>, and extract the project to a new folder

-   Add the new Azure DevOps project git repository as a new origin, using PowerShell or your favorite git client

-   Add all files to the local git repository (git add -A)

-   Commit your changes to the local repository, adding a new commit message (git commit -m "Initial commit")

-   Push to the remote repository (git push -u origin --all)

#### Exit criteria

-   Browse to the Code page of your Azure DevOps project. You should see the code you just pushed to the repository.

## Exercise 2: Configure Visual Studio App Center

**Duration**: 25 minutes

In this step, we'll explore how quick and easy it is to connect your mobile app to Visual Studio App Center. The App Center provides best in class mobile app monitoring, along with a CI, and mobile app testing solution to ensure that any issues in your app are identified and resolved quickly.

### Help references
|    |            |
|----------|:-------------|
| **Description** | **Links** |
| Visual Studio App Center | <https://docs.microsoft.com/en-us/appcenter/> |

### Task 1: Create a new iOS / Xamarin app

#### Tasks to complete

-   Browse to <https://appcenter.ms/apps>

-   Add a new iOS app, indicating the Xamarin platform

#### Exit criteria

-   You have a new iOS app with an identifying name, such as Contoso Baggage \[iOS\]

### Task 2: Connect iOS app to App Center

Add the App Secret key to the ContosoBaggage.iOS Xamarin project in Visual Studio.

#### Tasks to complete

-   In App Center, select the iOS app you created

-   Scroll down the Getting Started page to locate and copy the App Secret key

-   Open the ContosoBaggage solution in Visual Studio

-   Open the **AppDelegate.cs** file within the **ContosoBaggage.iOS** project

-   Locate the **FinishedLaunching()** method, and paste your App Secret key as a parameter to the AppCenter.Start method

#### Exit criteria

-   You replaced the existing sample App Secret key within the AppDelegate class of the ContosoBaggage.iOS project with the key generated for your new iOS app in App Center.

### Task 3: Create a new Android / Xamarin app

#### Tasks to complete

-   Browse to <https://appcenter.ms/apps>

-   Add a new Android app, indicating the Xamarin platform

#### Exit criteria

-   You have a new Android app with an identifying name, such as Contoso Baggage \[Android\]

### Task 4: Connect Xamarin.Android app to App Center

Add the App Secret key to the ContosoBaggage.Droid Xamarin project in Visual Studio.

#### Tasks to complete

-   In App Center, select the Android app you created

-   Scroll down the Getting Started page to locate and copy the App Secret key

-   Open the ContosoBaggage solution in Visual Studio

-   Open the **MainActivity.cs** file within the **ContosoBaggage.Droid** project

-   Locate the **OnCreate()** method, and paste your App Secret key as a parameter to the AppCenter.Start method

#### Exit criteria

-   You replaced the existing sample App Secret key within the MainActivity class of the ContosoBaggage.Android project with the key generated for your new Android app in App Center.

### Task 5: Commit your changes to Azure DevOps

Update the git repository in your Azure DevOps project with the changes you just made to your solution.

#### Tasks to complete

-   Using the Team Explorer in Visual Studio, enter comments for your commit, and then commit all changes

-   Sync your changes to the git repository in Azure DevOps

#### Exit criteria

-   You can see your updated code changes in your Azure DevOps project

### Task 6: Connect iOS & Android apps in App Center to Azure DevOps and configure/launch build

Link your iOS and Android apps in App Center to your Azure DevOps project to use as the source for app builds.

#### Tasks to complete

-   Open your iOS app in App Center and link your ContosoBaggage Azure DevOps project to it within the Build configuration

-   Configure build on the master branch

-   Select the **ContosoBaggage.iOS.csproj** file as the project within the build configuration

-   Repeat the same steps to configure the build settings for the Android project, while pointing to the ContosoBaggage.Droid.csproj project file in its build configuration

#### Exit criteria

-   Both iOS and Android apps successfully build from the latest changes in your Azure DevOps project git repository.

### Task 7: Enable Telemetry (App Insights in App Center)

One of the most powerful features of Visual Studio App Center is the ability to connect your analytics data into Application Insights for further slicing and dicing of your data.

#### Tasks to complete

-   Select your profile in App Center and go to Account Settings

-   Attach your Azure subscription, if it is not already

-   Assign both iOS and Android apps to your Azure subscription

-   Connect Application Insights to your apps, exporting to your linked Azure subscription

#### Exit criteria

-   Both iOS and Android apps are assigned to your Azure subscription, and both are configured to send telemetry data to Application Insights

## Exercise 3: Configure Azure Cosmos DB and Azure functions

**Duration**: 30 minutes

Now that we've configured source control, crash reporting, and build steps for our mobile app, we can move on to deploying our backend. For this backend, we're going to leverage Azure Functions, which allows us to turn on micro services that you're only charged for when a call is made. With sub-second billing and multiple trigger options, Functions is a great way to modularize your backend and only pay for exactly the resources you use.

### Help references
|    |            |
|----------|:-------------|
| **Description** | **Links** |
| Azure Functions | <https://docs.microsoft.com/en-us/azure/azure-functions/> |
| Azure Cosmos DB | <https://docs.microsoft.com/en-us/azure/cosmos-db/introduction> |
|

### Task 1: Configure your Cosmos DB instance

#### Tasks to complete

-   Create a new Azure Cosmos DB instance, using the SQL API

#### Exit criteria

-   Your new Azure Cosmos DB instance is provisioned, and you have copied the URI and PRIMARY KEY values from the Read-write Keys tab within the Keys blade

### Task 2: Create collections in your Cosmos DB instance

Now that you've created your cosmos instance, we'll want to create collections for data to be written to.

#### Tasks to complete

-   Create a new collection with a database id of **bagDatabase**, collection id of **FlightCollection**, a throughput of 500 RU/s, and a fixed storage capacity.

-   Create a new collection with a database id of **bagDatabase**, collection id of **BagCollection**, a throughput of 500 RU/s, and a fixed storage capacity.

#### Exit criteria

-   You have two new collections added to your Cosmos DB instance, as seen in the Data Explorer

### Task 3: Create a new Application Insights instance

We are going to use Application Insights to monitor your backend project. In these steps, we will create a new instance of Application Insights to use later in our backend.

#### Tasks to complete

-   Create a new Application Insights instance in the portal, and select ASP.NET web application as the application type.

#### Exit criteria

-   You have a new Application Insights instance, and have copied its Instrumentation Key for later

### Task 4: Create a new Azure Function App

#### Tasks to complete

-   Create a new Function App, and add it to the resource group you have been using for this lab

#### Exit criteria

-   You have a new Function App that you will deploy to from Visual Studio

### Task 5: Connect your function project to Cosmos DB

#### Tasks to complete

-   In Visual Studio, open the **ContosoBaggage.Backend.Functions.sln** solution from the src/Backend folder where you extracted the lab files

-   Paste the URI value you copied from the Cosmos DB Read-write Keys tab as the value of **Url** within the **Cosmos** class in **Keys.cs**

#### Exit criteria

-   Make sure that your project compiles and launches. If prompted to download the Functions CLI Tools or .NET Framework, select **yes** for both options.

### Task 6: Connect your project to Application Insights

#### Tasks to complete

-   Paste the Application Insights Instrumentation Key you copied earlier, as the value of??**Key** within the **Analytics** class??in **Keys.cs**

#### Exit criteria

-   Your project has been configured to send telemetry to Application Insights

### Task 7: Add functions to your app

In this task, you will add three new functions to your Function App in Visual Studio

#### Tasks to complete

-   With your ContosoBaggage.Backend.Functions solution still open in Visual Studio, add three new Azure Functions to the Functions folder: **GetBaggageForFlight**, **GetFlights**, and **ReadIoTScannerMessages**. All three should have an **Http trigger** and **Anonymous** access rights.

-   Open **GetBaggageForFlight.cs** and replace the contents with the following code:

    ```csharp
    using System;
    using System.Linq;
    using System.Net;
    using System.Net.Http;

    using Microsoft.ApplicationInsights.DataContracts;
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Extensions.Http;
    using Microsoft.Azure.WebJobs.Host;
    using Microsoft.WindowsAzure.Storage.Table;

    using ContosoBaggage.Backend.Functions.Services;

    namespace ContosoBaggage.Backend.Functions.Functions
    {
        /// <summary>
        /// Get baggage for flight.
        /// </summary>
        public static class GetBaggageForFlight
        {
            /// <summary>
            /// Run the specified req and log.
            /// </summary>
            /// <returns>The run.</returns>
            /// <param name="req">Req.</param>
            /// <param name="log">Log.</param>
            [FunctionName("GetBaggageForFlight")]
            public static HttpResponseMessage Run([HttpTrigger(AuthorizationLevel.Anonymous, "get", 
                                                    Route = nameof(GetBaggageForFlight))]HttpRequestMessage req, 
                                                    TraceWriter log)
            {
                using (var analytic = new AnalyticService(new RequestTelemetry
                {
                    Name = nameof(GetBaggageForFlight)
                }))
                {
                    try
                    {
                        var kvps = req.GetQueryNameValuePairs();
                        var flightNumber = kvps.FirstOrDefault(kvp => kvp.Key == "flightNumber").Value;

                        var baggageForFlight = CosmosDataService.Instance("BagCollection").GetBaggageForFlight(flightNumber);

                        if (baggageForFlight.Count == 0)
                            return req.CreateErrorResponse(HttpStatusCode.NoContent, "No results found for flight");                    

                        return req.CreateResponse(HttpStatusCode.OK, baggageForFlight);
                    }
                    catch (Exception e)
                    {
                        // track exceptions that occur
                        analytic.TrackException(e);
                        return req.CreateErrorResponse(HttpStatusCode.BadRequest, e.Message, e);
                    }
                }
            }
        }
    }
    ```

-   Open **GetFlights.cs** and replace the contents with the following code:

    ```csharp
    using System;
    using System.Linq;
    using System.Net;
    using System.Net.Http;
    using System.Threading.Tasks;

    using Microsoft.ApplicationInsights.DataContracts;
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Extensions.Http;
    using Microsoft.Azure.WebJobs.Host;

    using ContosoBaggage.Backend.Functions.Services;

    namespace ContosoBaggage.Backend.Functions.Functions
    {
        public static class GetFlights
        {
            [FunctionName("GetFlights")]
            public static async Task<HttpResponseMessage> Run([HttpTrigger(AuthorizationLevel.Anonymous, "get", Route = nameof(GetFlights))]HttpRequestMessage req, TraceWriter log)
            {
                using (var analytic = new AnalyticService(new RequestTelemetry
                {
                    Name = nameof(GetFlights)
                }))
                {
                    try
                    {
                        var flights = CosmosDataService.Instance("FlightCollection").GetFlights();

                        return req.CreateResponse(HttpStatusCode.OK, flights);
                    }
                    catch (Exception e)
                    {
                        // track exceptions that occur
                        analytic.TrackException(e);
                        return req.CreateErrorResponse(HttpStatusCode.BadRequest, e.Message, e);
                    }
                }
            }
        }
    }
    ```

-   Open **ReadIoTScannerMessages.cs** and replace the contents with the following code:

    ```csharp
    using ContosoBaggage.Backend.Functions.Services;
    using ContosoBaggage.Common.Models;
    using Microsoft.ApplicationInsights.DataContracts;
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Host;
    using Microsoft.Azure.WebJobs.ServiceBus;
    using Newtonsoft.Json;
    using Newtonsoft.Json.Linq;
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Threading.Tasks;

    namespace ContosoBaggage.Backend.Functions.Functions
    {
        public static class ReadIoTScannerMessages
        {
            [FunctionName("ReadIoTScannerMessages")]
            public async static void Run([EventHubTrigger("appinnovationhub", Connection = "EventHub")]string myEventHubMessage, TraceWriter log)
            {
                using (var analytic = new AnalyticService(new RequestTelemetry
                {
                    Name = nameof(ReadIoTScannerMessages)
                }))
                {
                    try
                    {
                        log.Info($"C# Event Hub trigger function processed a message: {myEventHubMessage}");

                        BaggageItem baggageItem = JsonConvert.DeserializeObject<BaggageItem>(myEventHubMessage);

                        // Check if the event hub message id is the same as an item already in the database. 
                        // If yes, update that record, if not, create a new record
                        var baggageForFlight = CosmosDataService.Instance("BagCollection").GetBaggageForFlight(baggageItem.FlightNumber);
                        var matches = baggageForFlight.Where(b => String.Equals(b.Id, baggageItem.Id)).ToList();

                        if ((baggageForFlight != null) && (matches.Count != 0))
                        {
                            await CheckIfBagAlreadyExists(baggageForFlight, baggageItem);
                        }
                        else
                        {
                            Console.WriteLine("No matches found. The database is likely corrupt. " +
                            "Try deleting the collections in the database and running setup in the IOTHubGettingStarted Project under Program.exe");
                        }
                    }
                    catch (Exception e)
                    {
                        // track exceptions that occur
                        analytic.TrackException(e);
                    }
                }
            }

            public static async Task CheckIfBagAlreadyExists(List<BaggageItem> baggageForFlight, BaggageItem baggageItem)
            {
                // If the baggage has the same status, return, otherwise update its status
                if (baggageForFlight.Contains(baggageItem))
                {
                    return;
                }
                else
                {
                    await CosmosDataService.Instance("BagCollection").UpdateItemAsync(baggageItem);
                }
            }
        }
    }
    ```

#### Exit criteria

-   You can successfully compile the solution

### Task 8: Deploy your app to Azure

#### Tasks to complete

-   Publish your Functions project to your existing Azure Function App in Azure

-   Modify the publish profile settings to use the Debug \| Any CPU configuration. This allows you to attach a remote debugger for development only. This should not be set for production deployments.

#### Exit criteria

-   After publishing, copy the site URL and verify the function is running by pasting it in a new browser window or creating a GET request in Postman. There will be no data since we haven't populated the databases, but this will at least confirm that your project is deployed successfully and running in Azure with no errors.

## Exercise 4: Setup IoT hub

**Duration**: 20 minutes

Azure IoT Hub is a fully managed Azure service. This service enables reliable and secure bi-directional communications between millions of Internet of Things (IoT) devices and a solution back end. One of the biggest challenges that IoT projects face is how to reliably and securely connect devices to the solution back end. To address this challenge, IoT Hub:

-   Offers reliable device-to-cloud and cloud-to-device hyper-scale messaging

-   Enables secure communications using per-device security credentials and access control

-   Includes device libraries for the most popular languages and platforms

This tutorial shows you how to:

-   Use the Azure portal to create an IoT hub

-   Create a device identity in your IoT hub

-   Create a simulated RFID device sends messages to your IoT Hub

In this task you will find three projects:

-   **CreateDeviceIdentity**, which creates a device identity and associated security key to connect your device app

-   **SimulatedDevice**, which connects to your IoT hub with the device identity created earlier, and sends a telemetry message every second by using the MQTT protocol

-   **Telemetry**, which if you opt in, Microsoft will get usage about how you use IoT Hub

### Help references
|    |            |
|----------|:-------------|
| **Description** | **Links** |
| Routing messages from IoT hub to a queue | <https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-csharp-csharp-process-d2c> |
| IoT Hub and the MQTT protocol | <https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-mqtt-support> |
|

### Task 1: Create the IoT hub in Azure

Create an IoT Hub for your simulated device app to connect to

#### Tasks to complete

-   Create an IoT Hub instance from within Azure

-   Select the **F1 -- Free** tier for this lab

-   Copy the Hostname value

-   Copy the IoT Hub connection string from the iothubowner shared access policy

#### Exit criteria

-   You have now created your IoT hub, and you have the host name and IoT Hub connection string that you need to complete the rest of this tutorial

### Task 2: Create a device identity

In this task, you will create a .NET console app that creates a device identity in the identity registry in your IoT hub. A device cannot connect to IoT hub unless it has an entry in the identity registry. For more information, see the \"Identity registry\" section of the [IoT Hub developer guide](https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-devguide-identity-registry). When you run this console app, it generates a unique device ID and key. Your device uses these values to identify itself when it sends device-to-cloud messages to IoT Hub. Device IDs are case-sensitive.

#### Tasks to complete

-   In Visual Studio, open the **IoTHubGetStarted.sln** solution from the src/IoTSimulator folder where you extracted the lab files

-   Update the **ConnectionString** variable within the Program.cs file of the **CreateDeviceIdentity** project with your IoT Hub connection string you copied in the previous task

#### Exit criteria

-   Run the CreateDeviceIdentity program, then copy the generated device key. You will use this value later.

### Task 3: Set up the backend keys for the database and Functions

#### Tasks to complete

-   Open the **Keys.cs** file within the **SimulatedDevice** project

-   Paste the URI value you copied from the Cosmos DB Read-write Keys tab as the value of **Url** within the **Cosmos** class in **Keys.cs**

-   Paste the Application Insights Instrumentation Key you copied earlier, as the value of??**Key** within the **Analytics** class??in **Keys.cs**

-   Expand the Services folder and open **FlightService.cs**

-   Copy your Function App URL and paste the value into the base URL (line 17). Be sure to keep the {0} on the end of the string.

#### Exit criteria

-   Your simulated device project is configured to access Cosmos DB and send data to your Azure Functions

### Task 4: Set up the program to scan the bags

#### Tasks to complete

-   In the IoTHubGetStarted Visual Studio project, open **Program.cs** within the **SimulatedDevice** project. Update the **Program** class with the following:

    -   Substitute {iot hub hostname} with the IoT hub host name you retrieved in the \"Create an IoT hub\" section

    -   Substitute {device key} with the device key you retrieved in the \"Create a device identity\" section

#### Exit criteria

-   The SimulatedDevice project is configured to send data to your IoT Hub instance on behalf of the simulated device identity you created earlier

### Task 5: Run the program to scan the bags

#### Tasks to complete

-   Around line 35, enter in the Flight that you would like to update the bags for

```csharp
static string myFlightNumber = "FL1234";
```

-   Run the **SimulatedDevice** project. You should see the bags updating in the Console app. The backend might take a few minutes to set up.

    ![Bag updates are displayed in the Console app after running the SimulatedDevice project.](images/Hands-onlabunguided-Mobileappinnovationimages/media/image12.png "Run the SimulatedDevice project")

#### Exit criteria

-   The **Usage** tile in the [Azure portal](https://portal.azure.com/) shows the number of messages sent to the IoT hub:

    ![This is a screenshot of the Usage tile.](images/Hands-onlabunguided-Mobileappinnovationimages/media/image13.png "View the Usage tile")

## Exercise 5: Connect the mobile app to the backend

**Duration**: 30 minutes

Now that we've configured backend and populated it with data, we'll configure our mobile app to be able to consume the data from our Functions.

### Task 1: Connect app to Azure backend

#### Tasks to complete

-   Open the **ContosoBaggage.sln** solution from your /src/ContosoBaggage folder of your project

-   Open FlightService.cs under the Services folder of the ContosoBaggage project

-   Update the \_baseUrl with your Function App URL. Make sure to preserve the {0} at the end of the URL

#### Exit criteria

-   Your mobile app is configured to connect to your Azure Functions

### Task 2: Create a Fight List page

#### Tasks to complete

-   Add a new Xamarin.Forms \> Content Page item to the Pages folder of the ContosoBaggage project. Name it FlightListPage.xaml.

-   Replace the contents of FlightListPage.xaml with the following:

    ```xml
     <?xml version="1.0" encoding="UTF-8"?>
    <pages:BaseContentPage 
    xmlns="http://xamarin.com/schemas/2014/forms" 
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    x:Class="ContosoBaggage.Pages.FlightListPage"
    xmlns:controls="clr-namespace:ContosoBaggage.Controls;assembly=ContosoBaggage"
    xmlns:pages="clr-namespace:ContosoBaggage.Pages;assembly=ContosoBaggage"
    xmlns:views="clr-namespace:ContosoBaggage.Views;assembly=ContosoBaggage"
    xmlns:viewmodels="clr-namespace:ContosoBaggage.ViewModels;assembly=ContosoBaggage"
    x:TypeArguments="viewmodels:FlightListViewModel"
    Title="{Binding Title}"
    BackgroundColor="#EFEEF5">
    <pages:BaseContentPage.Content>
        <Grid RowSpacing="0">
            <Grid.RowDefinitions>
                <RowDefinition Height="Auto" />
                <RowDefinition Height="150" />
                <RowDefinition Height="120" />
                <RowDefinition Height="1" />
                <RowDefinition Height="*" />
            </Grid.RowDefinitions>
            <views:NavigationBar
                CanMoveBack="true"
                Title="Add Treasure"
                BackgroundColor="White"/>

            <Image Source="header_other.jpg"
                Aspect="AspectFill"
                Grid.Row="1"/>
            <BoxView BackgroundColor="{StaticResource gray}"
                Grid.Row="1"
                Opacity="0.3"/>
            <ActivityIndicator 
                Grid.Row="2"
                HorizontalOptions="Center"
                VerticalOptions="Center"
                IsVisible="{Binding IsBusy}"
                IsRunning="{Binding IsBusy}"
                Color="{StaticResource gray}"/>
            <ListView x:Name="FlightListView"
                IsVisible="{Binding IsBusy, Converter={StaticResource notConverter}}"
                ItemsSource="{Binding Flights}"
                CachingStrategy="RetainElement"
                SeparatorVisibility="None"
                RowHeight="60"
                Grid.Row="4">
                <ListView.Behaviors>
                    <controls:EventToCommandBehavior EventName="ItemTapped" 
                        Command="{Binding FlightSelectedCommand}" 
                        EventArgsConverter="{StaticResource ItemTappedConverter}" />
                </ListView.Behaviors>

                <ListView.ItemTemplate>
                    <DataTemplate>
                        <ViewCell>
                            <controls:DataTemplatePresenter 
                            ItemTemplate="{StaticResource flightDetailsView}"/>
                        </ViewCell>
                    </DataTemplate>
                </ListView.ItemTemplate>
            </ListView>
        </Grid>

    </pages:BaseContentPage.Content>
    </pages:BaseContentPage >
    ```

#### Exit criteria

-   You have a new Flight List page ready to be connected to the Flight List view model you will create next

### Task 3: Create a Flight List view model

#### Tasks to complete

-   Add a new class named FlightListViewModel.cs to the ViewModels folder of the ContosoBaggage project

-   Replace the contents of the file with this code:

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Collections.ObjectModel;
    using System.Linq;
    using System.Threading.Tasks;
    using System.Windows.Input;

    using Xamarin.Forms;

    using Microsoft.AppCenter.Analytics;

    using ContosoBaggage.Common.Models;
    using ContosoBaggage.Services;
    using ContosoBaggage.Controls;
    using ContosoBaggage.Navigation;
    using ContosoBaggage.Models;

    namespace ContosoBaggage.ViewModels
    {
        /// <summary>
        /// Flight list view model.
        /// </summary>
        public class FlightListViewModel : BaseViewModel
        {
            /// <summary>
            /// Gets or sets the flights.
            /// </summary>
            /// <value>The flights.</value>
            public ObservableCollection<Flight> Flights { get; set; }

            /// <summary>
            /// The flight selected command.
            /// </summary>
            Command _flightSelectedCommand;

            /// <summary>
            /// Gets the flight selected command.
            /// </summary>
            /// <value>The flight selected command.</value>
            public Command FlightSelectedCommand
            {
                get => _flightSelectedCommand ?? (_flightSelectedCommand = new Command<Flight>((obj) => GoToPage(PageNames.FlightDetailsPage,
                                                            new NavigationParameters()
                {
                    {"flight", obj}
                })));
            }

            /// <summary>
            /// The get flights command.
            /// </summary>
            Command _getFlightsCommand;

            /// <summary>
            /// Gets the get flights command.
            /// </summary>
            /// <value>The get flights command.</value>
            public Command GetFlightsCommand
            {
                get => _getFlightsCommand ??
                (_getFlightsCommand = new Command(async () => await ExecuteGetFlightsCommand(), 
                                                () => { return !IsBusy; }));
            }

            /// <summary>
            /// Executes the get flights command.
            /// </summary>
            /// <returns>The get flights command.</returns>
            private async Task ExecuteGetFlightsCommand()
            {
                if (IsBusy)
                    return;

                IsBusy = true;
                GetFlightsCommand.ChangeCanExecute();
                try
                {
                    Flights.Clear();

                    var flights = await FlightService.GetFlights();
                    foreach (var flight in flights.OrderByDescending(x => x.FlightDate))
                    {
                        Flights.Add(flight);
                    }
                }
                catch (Exception ex)
                {
                    Analytics.TrackEvent("Exception", new Dictionary<string, string> {
                        { "Message", ex.Message },
                        { "StackTrace", ex.ToString() }
                    });
                }
                finally
                {
                    IsBusy = false;
                    GetFlightsCommand.ChangeCanExecute();
                }
            }

            /// <summary>
            /// Initializes a new instance of the <see cref="T:ContosoBaggage.ViewModels.FlightListViewModel"/> class.
            /// </summary>
            public FlightListViewModel()
            {
                Title = "Flights";

                Flights = new ObservableCollection<Flight>();
            }
        }
    }
    ```

#### Exit criteria

-   You have a new Flight List view model

### Task 4: Connect the view model to the page

#### Tasks to complete

-   Open the FlightListPage.xaml.cs file

-   Replace the implementation of the FlightListPage class with the following code:

    ```csharp
    using ContosoBaggage.Controls;
    using ContosoBaggage.ViewModels;
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    using Xamarin.Forms;
    using Xamarin.Forms.Xaml;

    namespace ContosoBaggage.Pages
    {
	    [XamlCompilation(XamlCompilationOptions.Compile)]
        public partial class FlightListPage : BaseContentPage<FlightListViewModel>, INavigableXamarinFormsPage
        {
            public FlightListPage()
            {
                InitializeComponent();
            }

            protected override void OnAppearing()
            {
                base.OnAppearing();

                if (ViewModel.Flights.Count > 0 || ViewModel.IsBusy)
                    return;

                ViewModel.GetFlightsCommand.Execute(null);
            }
        }
    }
    ```

#### Exit criteria

-   Your Flight List page and view model are now linked

### Task 5: Add Flight List page to the navigation service

#### Tasks to complete

-   Open the **NavigationService.cs** within the Navigation folder of the ContosoBaggage project

-   Find the **GetPage** method and uncomment the **return new FlightListPage();** line

#### Exit criteria

-   You can navigate to your new Flight List page from within the app

### Task 1: Run the app and verify that it successfully retrieves flight data

#### Tasks to complete

-   Set either the iOS or Android app as your StartUp project, whichever you plan to debug

-   Launch the app within a simulator

#### Exit criteria

-   You are able to successfully launch the mobile app within a simulator and view your baggage information

    ![This is a screenshot of the app running on a smartphone.](images/Hands-onlabunguided-Mobileappinnovationimages/media/image14.png "App screenshot")

## After the hands-on lab

**Duration**: 10 minutes

In this exercise, attendees will deprovision any Azure resources that were created in support of the lab.

### Task 1: Delete the resource group in which you placed your Azure resources.

1.  From the Portal, navigate to the blade of your Resource Group and select **Delete** in the command bar at the top

2.  Confirm the deletion by re-typing the resource group name and selecting Delete

You should follow all steps provided *after* attending the hands-on lab.