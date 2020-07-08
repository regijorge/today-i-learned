# SNS - Simple Notification Service
* Paging in the cloud
* Uses publish-subscribe mechanism based on "Topics"
  * Called pub-sub messaging
* Several delivery options supported
  * HTTP/HTTPS
  * E-mail
  * SMS (text message)
  * Lambda

### Message limits
* Up to 256 kb of data

### Topic
* A topic is a place to put some message
* Examples
  * Admin alerts
  * Performance alerts
  * User created/deleted alerts
  * Order created/updated alerts

### Publishers
* Publishers push message to Topics
* Examples
  * Cloudwatch
  * Cost explorer

### Subscribers
* Clients receiving notifications
* Receive all messages broadcasted to the topic
* Examples
  * Lambda
  *