# Introduction to Cloud Functions
**Cloud Functions and Cloud Run are both serverless compute optiosn. Cloud run supports both services with HTTP endpoints than run continuously and batch jobs that run to completino and terminate, whereas cloud functions are relativley short running functions (60 mins for HTTP functions and 10 mins for event-driven functions)**

***Pub/Sub***
Pub/Sub stands for Publish/Subscribe, which is a messaging pattern used in software architecture where senders of messages (publishers) do not directly send messages to specific receivers (subscribers). Instead, they categorize published messages into classes without knowledge of which subscribers, if any, there may be. Similarly, subscribers express interest in one or more classes and only receive messages that are of interest, without knowledge of which publishers, if any, there are.

Here's a simple example to illustrate how Pub/Sub works:

Let's say you have a news website with various categories like Sports, Politics, Technology, and Entertainment. Users can subscribe to the categories they are interested in, and whenever a new article is published in a category they are subscribed to, they receive a notification.

- **Publishers**: These are the news writers or editors who write articles. When they publish an article, they don't need to know who will read it. They simply categorize the article based on its content, such as Sports, Politics, etc., and send it to the appropriate channel.

- **Subscribers**: These are the users who are interested in specific categories of news. They subscribe to the categories they want to receive notifications for.

- **Message Broker**: This is the middleman that manages the communication between publishers and subscribers. It receives messages from publishers and delivers them to subscribers based on their interests.

Here's how the process works:

1. **Publisher publishes an article**: Let's say a sports journalist writes an article about a recent football match. The publisher categorizes it under "Sports" and sends it to the message broker.

2. **Message broker receives the article**: The message broker receives the article and knows that it belongs to the "Sports" category.

3. **Message broker delivers the article to subscribers**: The message broker checks its list of subscribers interested in the "Sports" category and sends the article to those subscribers.

4. **Subscribers receive the article**: Users who are subscribed to the "Sports" category receive a notification or see the article in their feed.

This way, the publisher doesn't need to know anything about the subscribers, and the subscribers don't need to know anything about the publishers. They are decoupled from each other, which makes the system more scalable and flexible.

## Events, Triggers, and Functions

- Events: particular action that happens in the cloud, such as a file is uploaded ot cloud storage, or message that is written to a pub/sub message queue. (HTTP, Cloud storage, Cloud pub/sub, cloud Firestore, Cloud Firebase)
- Second generation of cloud function use Eventarc triggers,  which are configured based on a provider
- Trigger: a way of responding to an event
- Function: triggers have an associated function, the function passed arguments with data about the event, executes in response to the event.


## Runtime Environment
- Functions run in their own environment. Each time a function is invoked, it is run in a separate instance from all other invocations. 
- There is no way to share information between invocations of functions using only cloud functions. if you need cordination, you need to confugure cloud firestore or cloud storage


# Cloud Functions Receiving Events from Cloud Storage
## Deploying with console
## Deploying with gcloud commands

# Cloud Functions Receiving Events from Pub/Sub
## Deploying with console
## Deploying with gcloud commands


