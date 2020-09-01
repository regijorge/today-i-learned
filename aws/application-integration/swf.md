# SWF - Simple WorkFlow
* Defines a sequence of events required to achieve a workflow
* Used in decoupled applications

## Workflow
* Activities that result in a desired objective
* Logic that controll the acitivities
  * Decider function determines the best workflow
* Operates in a Domain
  * Created logical boundary in SWF to constrain the scope of the activities

## Activity tasks
* One invocation of an activity
  * Example: processing an order
* May be invoked multiple times
  * Example: processing multi-item order

## Activity workers
* The applications that receive and process the activity tasks