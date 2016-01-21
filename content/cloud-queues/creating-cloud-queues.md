---
node_id: 3683
title: Creating Cloud Queues
type: article
created_date: '2013-09-16'
created_by: Megan Meza
last_modified_date: '2016-01-05'
last_modified_by: Mike Asthalter
product: Cloud Queues
product_url: cloud-queues
---

Creating a Cloud Queue can be accomplished through the Control Panel or
through your terminal.  After creating the Queue, you can use the
Control Panel for viewing Queue details or deleting the Queue as
needed.  All other Queue commands will be completed through the
terminal.

**Note**: Be sure to [set up your authentication
token](/how-to/cloud-queues-curl-cookbook)
before completing the terminal steps for creating your cloud queue.

#### In the Control Panel

-   In the Queues tab of the Control Panel, click **Create Queue**.
-   In the pop out box, enter a name for your queue, select your
    preferred region and click **Create Queue**. (We are using
    &ldquo;samplequeue&rdquo; for our example queue name throughout these steps.)

When the queue is finished building, you will see the details for your
queue listed in the Control Panel. You will then need to complete the
steps under [Testing Your
Queue](/how-to/cloud-queues-curl-cookbook)
in your terminal to begin posting messages to your Queue.

#### Or, In Your Terminal

-   Enter the following request in your terminal:

<!-- -->

        $ curl -i -X PUT https://$ENDPOINT:443/v1/queues/samplequeue -H "X-Auth-Token: $TOKEN"

-   Watch for the following response:

<!-- -->

    HTTP/1.1 200 OK Content-Length: 140 Content-Type: application/json; charset=utf-8 Content-Location: /v1/queues {"queues": [{"href": "/v1/queues/samplequeue", "name": "samplequeue"}], "links": [{"href": "/v1/queues?marker=samplequeue", "rel": "next"}]}

####
Testing Your Queue

-   You can test your queue by posting a message to it:

<!-- -->

           $ curl -i -X POST https://$ENDPOINT:443/v1/queues/samplequeue/messages -d '
        [{"ttl": 300, "body": {"event": "one"}}]
        ' -H "Content-type: application/json" -H "Client-ID: e58668fc-26eb-11e3-8270-5b3128d43830" -H "X-Auth-Token: $TOKEN"

-   Watch for the following response to your test post:

<!-- -->

            HTTP/1.1 201 Created
        Content-Length: 93
        Content-Type: application/json; charset=utf-8
        Location: /v1/queues/samplequeue/51e840b61d10b20570d56ff4

        {"partial": false, "resources": ["/v1/queues/samplequeue/messages/51e840b61d10b20570d56ff4"]}

You have now created a Cloud Queue.

