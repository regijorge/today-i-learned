# SQS
* Used to decouple applications
  * Breaking application into separate processing tasks
  * Allows many small processes to form a complete solution


## SQS Messages
* Outputs from other process
* Inputs to other process
* Queued and processed asynchronously
* Up to 256kb data

## SQS Participants
* Message Producers
* Message Consumers
* Messaging service
  * SQS

## SQS features
* Redundante accross multiples AZs
  * Queued until processed
  * Retention to 14 days
* Automatically scales

## SQS queue types
* Standard
  * Default queue type
  * Does not guaranteed sequential delivery of messages because it is asynchronous
  * At-least-once. Delivery may be duplicated
* First-In First-Out (FIFO)
  * Guaranteed sequential (and not duplicated) delivery of messages
  * Supports fewer transactions per second
    https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-quotas.html
* Dead Letter Queue
  * Is the same as Standard, but there you can send failed messages to be reprocessed

## Delay Queues
* Postpone delivery of new messages for a number of seconds
* Messages sent to Delay Queue remain invisible to consumers for the duration of the delay period
* Default delay is 0 seconds, maximum is 900 (15 min)
