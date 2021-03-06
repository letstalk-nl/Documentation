# Webhooks

SMTPeter has a tab named `WEBHOOKS`, previously 
called Feedback Loops. Webhooks are processes that notify their 
user of events that happen in real time through HTTP POST. This allows 
you to always have the most recent results of your mailing.

While Webhooks are very useful, they should be used with caution as they 
can generate large amounts of calls. If you are unsure about your server 
capacity or do not need real-time feedback you can also view the 
[logfiles](./logfiles-smtpeter "How to retrieve SMTPeter logfiles") or 
use the [SMTP](./smtp-api) or [REST](./rest-api) APIs.

There are several types of Webhooks. The articles linked below explain 
these types in more detail:

* [Webhooks for bounces](webhook-bounces)
* [Webhooks for failures](webhook-failures)
* [Webhooks for clicks](webhook-clicks)
* [Webhooks for opens](webhook-opens)

## Webhooks in SMTPeter

Webhooks can be used to sync data that passes through Copernica 
directly into your own application. Webhooks require a script on 
your own server to execute whenever information is provided through the 
Webhook. You can set several triggers in the Webhooks tab such 
as opens, clicks, profile edits and bounces.

The data you receive is very rich and allows you to easily link it to the 
data already present in your system.

## Setting up Webhooks

The first step for setting up a Webhook is to navigate to the `WEBHOOK` 
tab. To create a Webhook you pick a type and then add the callback URL, where 
the data will be sent to after configuration.

The next step is to verify your web address. This extra step ensures that 
your potentially confidential data will be sent to the correct server. 
In SMTPeter you will find a link to download the verification file, 
which will be different for every new Webhook. The file should be placed 
in the root of your webserver or in the directory of the script that will 
handle the incoming HTTP POST requests. So if your script is in the following location:

```text
"https://example.com/dir/script.php"
```

You should have the text file, which will be named something like "smtpeter-xxxxx.txt" 
in the same location:

```text
"https://example.com/dir/smtpeter-xxxxx.txt"
```

You can now verify the callback URL by clicking the link in the dashboard. 
You may delete the text file after verification. You can test your new 
Webhook by clicking 'Manage' next to it and using the testing tool or 
the 'Check now' button in the Webhook menu to test all your Webhooks.

## Security

To protect your endpoint from abuse and false information injection, SMTPeter 
[signs all requests](./webhook-security) to your endpoint, so you can be sure 
it's actually SMTPeter sending you the data. 

## More information

* [Logfiles](./logfiles-smtpeter)
* [REST API](./rest-api)
* [SMTP API](./smtp-api)
* [Webhooks for bounces](webhook-bounces)
* [Webhooks for failures](webhook-failures)
* [Webhooks for clicks](webhook-clicks)
* [Webhooks for opens](webhook-opens)
