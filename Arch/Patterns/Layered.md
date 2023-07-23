#devOps #architecture #architecturePatterns
- [ ] Components(code) is separated into **layers** of subtasks
- [ ] Most common
- [ ] Layers (number of layers depends on the system)
	- [ ] **Presentation** layer
		- [ ] UI
	- [ ] **Business/Application** layer
		- [ ] handles aspects related to accomplishing functional requirements
	- [ ] **Domain** layer
		- [ ] responsible for algorithms, and programming components
	- [ ] **Persistence** layer
		- [ ] code to manipulate database. e.g: SQL statements
	- [ ] **Data** layer
    	- [ ] database
- [ ] Advantage
	- [ ] A lower layer can be **used by different** higher layers
	- [ ] layers make **standardization** easier
	- [ ] changes can be made within the layer **without affecting others**
- [ ] Disadvantages
	- [ ] **Not universal**ly applicable
	- [ ] certain **layers may have to be skipped** in certain situations
- [ ] Usage
	- [ ] **e-commerce** web applications
	- [ ] General **desktop applications**


## Layers of isolation (closed layers)
- [ ] Change made in one layer of architecture don't impact components in other layers
- [ ] If Presentation layer is allowed to directly access data layer, change in data layer will affect both presentation layer and persistence layer, there by producing a very tightly coupled application with lots of interdependencies.

## Open Layers
- [ ] sometimes an additional optional layer might be needed. it wouldn't make sense to pass all traffic through optional layer. so that layer will be kept open.
- [ ] open layers can be bypassed
![[Pasted image 20230226202845.png]]

## Example
![[Pasted image 20230226203926.png]]

## Considerations
- [ ] **Sinkhole** anti-pattern
    - [ ] situation where request simply flow through multiple layers of architecture with little or no logic performed within each layer.
    - [ ] if more than 20% requests are sinkhole, consider making some architecture layers open, keeping i mind that it will be more difficult to control change due to the lack of layer isolation.
- [ ] tends to lean towards **monolithic** applications

## Pattern Analysis
- [ ] Overall **Agility**: ==Low==
    - [ ] because of monolithic nature of most implementations and tight coupling of components making changes is cumbersome and time consuming.
- [ ] **Ease of Deployment**: ==Low==
    - [ ] small change to a component can require a redeployment of the entire application
- [ ] **Testability**: `High`
    - [ ] as other layers can be mocked, testing components in each layers is relatively easy
- [ ] **Performance**: ==Low==
    - [ ] to fulfill a business request, need to go through multiple layers of architecture
- [ ] **Scalability**: ==Low==
    - [ ] because of the trend towards tightly coupled monolithic implementations, scaling is difficult. even if each layer is separate physical deployment, overall granularity is too broad.
- [ ] **Ease of Development**: `High`
    - [ ] it's not too complex, and is aligned with general organization structures. 
    - [ ] **Conway's law**: organizations design systems that mirror their own communication structure