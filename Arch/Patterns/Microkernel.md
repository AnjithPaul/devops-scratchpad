#devOps #architecture #architecturePatterns 

- [ ] Many operating systems implement the micro‐ kernel architecture pattern, hence the origin of this pattern’s name.

- [ ] Usage
	- [ ] Product-based applications
    	- [ ] one that is packaged and made available for **download** in versions as a typical third-party product
	- [ ] scheduling applications
	- [ ] app development where **new features** are constantly added (like whatsapp and instagram)
    	- [ ] add additional application features as **plug-ins** to the core application, providing **extensibility** as well as feature **separation and isolation.**

## Components

### 1. Core System
- [ ] **Minimal functionality** required to make the system operational.

### 2. Plug-in Modules
- [ ] stand-alone, **independent** components that contain specialized processing, **additional features**, and custom code that is meant to enhance or **extend the core system** to produce additional business capabilities
- [ ] Core system can know what pulg-ins are available with **plug-in registry**
- [ ] ways to **connect** plug in to core system:
    - [ ] OSGi (open service gateway initative)
    - [ ] messaging
    - [ ] web services
    - [ ] direct point-to-point binding
- [ ] for third party plug-ins use **adapter** between.

## Considerations
- [ ] For product-based applications, always a good starting point. if the requirement evolve over time and the current architecture doesn't satisfy, then only refactor application to another architecture.
- [ ] Can be used in combination with other patterns such as layered pattern.

## Pattern Analysis

- [ ] Overall Agility: `High`
    - [ ] changes can be isolated and introduced quickly through **loosely coupled plug-in modules**
- [ ] Ease of Deployment: `High`
    - [ ] plug-in modules could be dynamically added to core system at runtime.
- [ ] Testability: `High`
    - [ ] Plug-in modules can be tested in **isolation** and can be easily **mocked**.
- [ ] Performance: `High`
    - [ ] you can customize and streamline applications to only include those features you need
- [ ] Scalability: ==LOW==
    - [ ] most microkernel architecture implementations are product based and are generally smaller in size, they are implemented as **single units** and hence not highly scalable
- [ ] Ease of Development: ==LOW==
    - [ ] requires **thoughtful design** and **contract** governance
    - [ ] Contract versioning, internal plug-in registries, plug-in granularity, and the wide choices available for plug-in connectivity all contribute to the complexity
- [ ] 