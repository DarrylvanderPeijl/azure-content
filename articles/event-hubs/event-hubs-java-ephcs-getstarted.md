<properties
	pageTitle="Get Started with Event Hubs in Java | Microsoft Azure"
	description="Follow this tutorial to get started using Azure Event Hubs; sending events with Java and receiving them in C# using the EventProcessorHost."
	services="event-hubs"
	documentationCenter=""
	authors="fsautomata"
	manager="timlt"
	editor=""/>

<tags
	ms.service="event-hubs"
	ms.workload="core"
	ms.tgt_pltfrm="na"
	ms.devlang="na"
	ms.topic="article"
	ms.date="03/08/2016"
	ms.author="sethm"/>

# Get started with Event Hubs

[AZURE.INCLUDE [service-bus-selector-get-started](../../includes/service-bus-selector-get-started.md)]

## Introduction

Event Hubs is a highly scalable ingestion system that can intake millions of events per second, enabling an application to process and analyze the massive amounts of data produced by your connected devices and applications. Once collected into Event Hubs, you can transform and store data using any real-time analytics provider or storage cluster.

For more information, see the [Event Hubs overview][].

This tutorial shows how to ingest messages into an Event Hub using a console application in Java, and to retrieve them in parallel using the C# [Event Processor Host][] library.

In order to complete this tutorial, you will need the following:

+ A Java development environment. For this tutorial, we will assume [Eclipse](https://www.eclipse.org/).

+ Microsoft Visual Studio Express for Windows

+ An active Azure account. <br/>If you don't have an account, you can create a free trial account in just a couple of minutes. For details, see <a href="http://azure.microsoft.com/pricing/free-trial/?WT.mc_id=A0E0E5C02&amp;returnurl=http%3A%2F%2Fazure.microsoft.com%2Fen-us%2Fdevelop%2Fmobile%2Ftutorials%2Fget-started%2F" target="_blank">Azure Free Trial</a>.

## Create an Event Hub

1. Log on to the [Azure classic portal][], and click **NEW** at the bottom of the screen.

2. Click **App Services**, then **Service Bus**, then **Event Hub**, then **Quick Create**.

	![][1]

3. Type a name for your Event Hub, select your desired region, and then click **Create a new Event Hub**.

	![][2]

4. Click the namespace you just created (usually ***event hub name*-ns**).

	![][3]

5. Click the **Event Hubs** tab at the top of the page, and then click the Event Hub you just created.

	![][4]

6. Click the **Configure** tab at the top of the page, add a rule named **SendRule** with *Send* rights, add another rule called **ReceiveRule** with *Manage, Send, Listen* rights, and then click **Save**.

	![][5]

7. On the same page, take note of the generated keys for **SendRule**.

	![][7]

8. Click the **Dashboard** tab at the top of the page, and then click **Connection Information**. Take note of the two connection strings.

	![][6]

Your Event Hub is now created, and you have the connection strings you need to send and receive events.

[AZURE.INCLUDE [service-bus-event-hubs-get-started-send-java](../../includes/service-bus-event-hubs-get-started-send-java.md)]


[AZURE.INCLUDE [service-bus-event-hubs-get-started-receive-ephcs](../../includes/service-bus-event-hubs-get-started-receive-ephcs.md)]

## Run the applications

Now you are ready to run the applications.

1.	Run the **Receiver** project from Visual Studio, then wait for it to start the receivers for all partitions.

	![][21]

2.	Run the **Sender** project, press **Enter** in the console window, and see the events appear in the receiver window.

	![][22]

## Next steps

Now that you've built a working application that creates an Event Hub and sends and receives data, you can move on to the following scenarios:

- A complete [sample application that uses Event Hubs][].
- The [Scale out Event Processing with Event Hubs][] sample.
- A [queued messaging solution][] using Service Bus queues.

For more information, see the [Java Developer Center](/develop/java/).

<!-- Images. -->
[1]: ./media/event-hubs-java-ephcs-getstarted/create-event-hub1.png
[2]: ./media/event-hubs-java-ephcs-getstarted/create-event-hub2.png
[3]: ./media/event-hubs-java-ephcs-getstarted/create-event-hub3.png
[4]: ./media/event-hubs-java-ephcs-getstarted/create-event-hub4.png
[5]: ./media/event-hubs-java-ephcs-getstarted/create-event-hub5.png
[6]: ./media/event-hubs-java-ephcs-getstarted/create-event-hub6.png
[7]: ./media/event-hubs-java-ephcs-getstarted/create-event-hub6b.png


[21]: ./media/event-hubs-java-ephcs-getstarted/run-csharp-ephcs1.png
[22]: ./media/event-hubs-java-ephcs-getstarted/run-csharp-ephcs2.png

<!-- Links -->
[Azure classic portal]: https://manage.windowsazure.com/
[Event Processor Host]: https://www.nuget.org/packages/Microsoft.Azure.ServiceBus.EventProcessorHost
[Event Hubs overview]: event-hubs-overview.md
[sample application that uses Event Hubs]: https://code.msdn.microsoft.com/Service-Bus-Event-Hub-286fd097
[Scale out Event Processing with Event Hubs]: https://code.msdn.microsoft.com/Service-Bus-Event-Hub-45f43fc3
[queued messaging solution]: ../service-bus/service-bus-dotnet-multi-tier-app-using-service-bus-queues.md
 