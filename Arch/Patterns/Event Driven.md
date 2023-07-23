#devOps #architecture #architecturePatterns 
- [ ] services of the software are **triggered by events**
- [ ] has highly **decoupled** single purpose **event processing components** that asynchronously **receive** and **process** events
- [ ] Event
	- [ ] user takes action
	- [ ] which causes a state change
	- [ ] and a reaction is generated which is the event.
- [ ] Usage
	- [ ] **JavaScript** website
	- [ ] **e-commerce** website

## Topologies

### 1.Mediator Topology
- used when you need to **orchestrate** multiple steps within an event through a **central** mediator
- e.g: a single event to **place a stock trade** might require you to first validate the trade, then check the compliance of that stock trade against various compliance rules, assign the trade to a broker, calculate the commission, and finally place the trade with that broker. All of these steps would require some level of **orchestration to determine the order of the steps** and which ones can be done serially and in parallel.

#### Components
1. Event **Queue**
    - Client sends an event to event queue, which takes it to event mediator.
    - e.g: It can be message queue, web service endpoint, or any combination of it
2. Event **Mediator**
    - Event mediator receives the **initial event** and orchestrates that event by sending **additional asynchronous events** to event channels to execute each step of the process
    - event mediator **doesn’t actually perform the business logic** necessary to process the initial event; rather, it knows of the steps required to process the initial event.
    - common implementation of the event mediator is through open source integration hubs such as **Spring Integration**, **Apache Camel**, or **Mule ESB**. For more sophisticated solution can implement using Business Process Manager like **jBPM**.
3. Event **Channels**
    - Carry additional asynchronous events to event processors.
    - can be either **message** **queues** or **message** **topics**
4. Event **Processors**
    - Listen to even channels and execute specific business logic to process events coming.
    - independent, highly **decoupled** component that perform a **specific task**.
    - granularity of the event-processor component can vary
![[Pasted image 20230301105512.png]]


### 2. Broker Topology
- used when you want to **chain** events together **without a central** mediator
- message flow is distributed across event processor components through **message broker** (e.g: ActiveMQ, HornetQ, etc.)
- useful when event processing flow is relatively **simple**

#### Components
1. **Broker**
    - Can be **centralized** or **federated**
    - Contains all of the event **channels** that are used within the flow.
    - Event channels contained can be message **queues**, message **topics**, or a **combination** of both
2. Event **Processor**

![[Pasted image 20230304134545.png]]


## Considerations

- [ ] **complex** to implement due to it's **asynchronous distributed** nature
- [ ] **distributed** architecture **issues**
    - [ ] remote process availability
    - [ ] lack of responsiveness
    - [ ] broker reconnection logic in the event of broker/mediator failure
- [ ] need to think about which **events** can and can't run **independently** and plan **granularity** of event processors accordingly.
    - [ ] if separate processor are used for something that should be an undivided transaction, that's probably not a right pattern.
- [ ] difficult to **create**, **maintain**, **govern** event-processor component **contracts**
- [ ] very important to settle on a standard **data format** (JSON, XML, Java Object, etc.) right from the start

## Pattern Analysis

- [ ] Overall **Agility**: `High`
    - [ ] as event processor components are **decoupled**, changes are **isolated** and can be made quickly without impacting other components.
- [ ] **Ease of Deployment**: `High`
    - [ ] relatively easy to deploy due to **decoupled** nature
    - [ ] broker topology is easier to deploy than mediator topology. becasue the event **mediator is tightly coupled**.
- [ ] **Testability**: ==Low==
    - [ ] require **specialized testing client** or tool to generate event
    - [ ] complicated because of **asynchronous** nature
- [ ] **Performance**: `High`
    - [ ] ability to perform **decoupled**, **parallel asynchronous** operations outweighs the cost of queuing and dequeuing the messages
- [ ] **Scalability**: `High`
    - [ ] each processor can be **scaled separately**, allowing for fine-grained scalability
- [ ] Ease of **Development**: ==Low==
    - [ ] **asynchronous** nature
    - [ ] **contract** creation
    - [ ] need more advanced **error handling** conditions within the code for unresponsive event processors and failed brokers