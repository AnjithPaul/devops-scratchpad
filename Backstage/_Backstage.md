**Platform to build Developer experience portal** 

## Motivation for developer experience portal
- [ ] backstage gives visibility to stuff
	- [ ] cloud provider metrics
	- [ ] APIs
	- [ ] etc
- [ ] knowledge sharing hub
- [ ] reduce time in setting up infra
	- [ ] frequency of change
		- [ ] if something gets introduced frequently backstage would be useful. if not frequent it won't give much value.
- [ ] helps standardisation.
	- [ ] for same problem different team could use different tools, create custom solutions, but backstage standardise it by giving a ready made solution.

## Building blocks of Engineering platform
- [ ] Delivery Infrastructure
	- [ ] iac, pipeline, observability, etc
- [ ] Service hub
	- [ ] publish and discover
		- [ ] API gateway
		- [ ] event hub
		- [ ] data models
- [ ] Developer hub
	- [ ] backstage
	- [ ] knowledge sharing hub
	- [ ] visibility to stuff

## pathway forBuilding engineering platform
- [ ] Technology strategy
	- [ ] Java, 
	- [ ] GCP, 
	- [ ] API strategy
- [ ] Engineering Practices & SOPs
	- [ ] Springboot, 
	- [ ] container on GKE using helm, 
	- [ ] setup kong API gateway
- [ ] Developer Experience portal
	- [ ] service template(springboot toolkit), 
	- [ ] on demand DI provisioning, 
	- [ ] product teams to publish and cosnume API as self service

## Features of engineerign platform
- [ ] product team (devs)
	- [ ] quick bootstrap
	- [ ] knowledge sharing hub
	- [ ] developer portal to setup infra
- [ ] cross functional teams (devops)
	- [ ] Internal open source
	- [ ] Automation
		- [ ] iac, pipeline as code
- [ ] executives
	- [ ] cost insights
	- [ ] compliance stuff .eg: cloud carbon footprint

## Catalog entities: 
### System modeling
- [ ] Component: 
	- [ ] software component
- [ ] API
	- [ ] interface exposed by a component
- [ ] Resource
	- [ ] infra resource
- [ ] system
	- [ ] collection of resource+component
	- [ ] exposes API
- [ ] Domain 
	- [ ] colelction of systems that share
		- [ ] terminology
		- [ ] domain models
		- [ ] business purpose
		- [ ] documentation

### Team organization
- [ ] User
	- [ ] A person
- [ ] Group
	- [ ] collection of users

### Entity as YAML
- [ ] similar to kubernetes resource.
	- [ ] kind: compononent

### Template
- [ ] template to build the component
- [ ] templates usually owned by platform team and the components created from it owned by specific app teams