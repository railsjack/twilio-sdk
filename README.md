<a href="https://www.twilio.com">
  <img src="https://static0.twilio.com/marketing/bundles/marketing/img/logos/wordmark-red.svg" alt="Twilio" width="250" />
</a>

# Twilio SDK Starter Application for Java

This sample project demonstrates how to use Twilio APIs in a Java web 
application. Once the app is up and running, check out [the home page](http://localhost:4567)
to see which demos you can run. You'll find examples for [Chat](https://www.twilio.com/chat), 
[Video](https://www.twilio.com/video), [Sync](https://www.twilio.com/sync), and more.

Let's get started!

## Configure the sample application

To run the application, you'll need to gather your Twilio account credentials and configure them
in a file named `.env`. To create this file from an example template, do the following in your
Terminal.

```bash
cp .env.example .env
```

Open `.env` in your favorite text editor and configure the following values.

### Configure account information

Every sample in the demo requires some basic credentials from your Twilio account. Configure these first.

| Config Value  | Description |
| :-------------  |:------------- |
`TWILIO_ACCOUNT_SID` | Your primary Twilio account identifier - find this [in the console here](https://www.twilio.com/console).
`TWILIO_API_KEY` | Used to authenticate - [generate one here](https://www.twilio.com/console/dev-tools/api-keys).
`TWILIO_API_SECRET` | Used to authenticate - [just like the above, you'll get one here](https://www.twilio.com/console/dev-tools/api-keys).

#### A Note on API Keys

When you generate an API key pair at the URLs above, your API Secret will only be shown once - 
make sure to save this information in a secure location, or possibly your `~/.bash_profile`.

### Configure product-specific settings

Depending on which demos you'd like to run, you may need to configure a few more values in your 
`.env` file.

### Configuring Twilio Sync

Twilio Sync works out of the box, using default settings per account. Once you have your API keys configured and your Java application built and running, [open a browser](http://localhost:4567/sync)!

### Configuring Twilio Chat

In addition to the above, you'll need to [generate a Chat Service](https://www.twilio.com/console/chat/services) in the Twilio Console. Put the result in your `.env` file.

| Config Value  | Where to get one. |
| :------------- |:------------- |
`TWILIO_CHAT_SERVICE_SID` | Chat | [Generate one in the Twilio Chat console](https://www.twilio.com/console/chat/services)

### Configuring Twilio Notify

You will need to create a Notify Service and add at least one credential on the [Mobile Push Credential screen](https://www.twilio.com/console/notify/credentials) (such as Apple Push Notification Service or Firebase Cloud Messaging for Android) to send notifications using Notify.

| Config Value   | Where to get one. |
| :------------- |:------------- |
`TWILIO_NOTIFICATION_SERVICE_SID` | Generate one in the [Notify Console](https://www.twilio.com/console/notify/services) and put this in your `.env` file.
A Push Credential | Generate one with Apple or Google and [configure it as a Notify credential](https://www.twilio.com/console/notify/credentials).

Once you've done that, run the application and [open a browser](localhost:4567/notify)!


## Run the sample application

This application uses the lightweight [Spark Framework](http://www.sparkjava.com), and
requires Java 8. 


Edit `.env` with the four configuration parameters we gathered from above. Export
the configuration in this file as system environment variables like so on Unix
based systems:

```bash
source .env
```

Now that the application is configured, we need to install our dependencies from Maven.

```bash
mvn install
```

And compile our application code:

```bash
mvn package
```


Now we should be all set! Run the application using the `java -jar` command.

```bash
java -jar target/sdk-starter-1.0-SNAPSHOT.jar
```

Your application should now be running at [http://localhost:4567/](http://localhost:4567/). 

![Home Screen](https://cloud.githubusercontent.com/assets/809856/26252870/0bfd80ac-3c77-11e7-9252-2b19dff5d784.png)

Check your config values, and follow the links to the demo applications!

## Running the SDK Starter Kit with ngrok

If you are going to connect to this SDK Starter Kit with a mobile app (and you should try it out!), your phone won't be able to access localhost directly. You'll need to create a publicly accessible URL using a tool like [ngrok](https://ngrok.com/) to send HTTP/HTTPS traffic to a server running on your localhost. Use HTTPS to make web connections that retrieve a Twilio access token.

```bash
ngrok http 4567
```

## License
## web: java -cp target/classes:target/dependency/* com.twilio.ServerApp
## web: java -jar target/sdk-starter-1.0-SNAPSHOT.jar -Dserver.port=$PORT
MIT
