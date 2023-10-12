
## *<u><strong>Original Setup</strong></u>*

***Three electable nodes in East.***

Primary - [liftoffbeta-shard-00-00-ikq7t.mongodb.net](http://liftoffbeta-shard-00-00-ikq7t.mongodb.net)

Secondary1 - [liftoffbeta-shard-00-01-ikq7t.mongodb.net](http://liftoffbeta-shard-00-01-ikq7t.mongodb.net)

Secondary2 - [liftoffbeta-shard-00-02-ikq7t.mongodb.net](http://liftoffbeta-shard-00-02-ikq7t.mongodb.net)

***One Readonly node in West.***

Read-only - [liftoffbeta-shard-00-03-ikq7t.mongodb.net](http://liftoffbeta-shard-00-03-ikq7t.mongodb.net)

Average response time recorded for *Initiate Conversation was **144ms***



<u style="font-size: 20.0px;letter-spacing: -0.008em;"><span style="color: rgb(70,76,79);"><em><strong>Fail-over</strong></em>:</span></u>

Moved the electable nodes to us-west-2 as below on cluster configuration page.

<ac:image ac:height="250"><ri:attachment ri:filename="image2019-7-10_12-33-33.png"><ri:page ri:space-key="~pvarga" ri:content-title="Mongo Cluster Fail-over Testing - Conversation History"></ri:page></ri:attachment></ac:image>



This failover process took around 20 minutes. It brings down the nodes in east and recreates the same nodes in west. Mongo automatically syncs the data between these nodes.

***Failed-over Nodes:***

***3 electable nodes and 1 read-only node in us-west-2***

Read-only - [liftoffbeta-shard-00-03-ikq7t.mongodb.net](http://liftoffbeta-shard-00-03-ikq7t.mongodb.net/)

Primary - [liftoffbeta-shard-00-00-ikq7t.mongodb.net](http://liftoffbeta-shard-00-00-ikq7t.mongodb.net/)

Secondary1 - [liftoffbeta-shard-00-01-ikq7t.mongodb.net](http://liftoffbeta-shard-00-01-ikq7t.mongodb.net/)

Secondary2 - [liftoffbeta-shard-00-02-ikq7t.mongodb.net](http://liftoffbeta-shard-00-02-ikq7t.mongodb.net/)

***No nodes in east***

The replica set name still remains the same as [liftoffbeta-ikq7t.mongodb.net](http://liftoffbeta-ikq7t.mongodb.net)

We didn't require any change from application side. We established VPC peering from Liftoff East VPC to Mongo West region. The average response time increased **(approx. 400ms)** as the application stack was in East and the mongo cluster was running in West. We noticed a couple of errors during this process which are documented <ac:link><ri:page ri:space-key="~pvarga" ri:content-title="MongoDB Failover Testing Errors"></ri:page><ac:plain-text-link-body><![CDATA[here]]></ac:plain-text-link-body></ac:link>



## <u><em><strong><span style="color: rgb(70,76,79);">Fail - back:</span></strong></em></u>

We restored the cluster to it's original form from cluster configuration settings page.


