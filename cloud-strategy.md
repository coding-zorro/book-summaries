# Cloud Strategy

Adopting a cloud strategy is like a change in lifestyle or moving to another country. We have to make significant adaptations to the new conditions. Some of them are:
- Budgeting is elastic, instead of being predicted
- Shoot for global optimization, instead of local
- Operating model is apps and infra together.
- Resilience is built through automation
- Scope is the whole platform instead of component
- Compliance is transparent instead of being controlling


### First Derivative
Digital transformation is not about making digital clones of offline processes. Digital companies redefine the whole business model by leveraging technology. How do they find the right business model though? They do not have the luxury of a well defined target state, and exist in a world of constant change. Digital companies embrace economies of speed(by quick experimentation, learning and course correction) and not scale.

### Wishful Thinking
Wishing for things is free. Two things help us translate wishes into reality - Strategy and Goals. Some points on this:
- Strategies will help you in making your wishes come true.
- Goals will help you know whether you are heading in the right direction and making good progress.
- Strategy is also about a series of meaningful decisions. 
- Strategy is also defined by what you're not doing.

Three elements of a strategy:
- You need to set priorities
- You need to balance your plan with opportunities that might come along.
- You need to allocate resources along with your strategy.

### Principles
Consistency in decision models are possible through principles. The principles are derived from the strategy. Principles on defining principles:
- If the opposite of a principle is nonsense, then its not a good principle.
- Principles that include product names or specific architectures, it runs the risk of decisions wanting to be elevated to principles.
- Principles should pass the test of time
- Principles should employ parallelism, meaning they should use the same grammatical constructs.
- Principles should be memorable
- Should only be a handful of principles, not more than that.

**High Level Principles**
- Multicloud doesn't mean uniform cloud
- Waiting for cloud evolution can be a viable strategy

**Specific High Level Principles**
- Use before reuse
- Design from front to back

### Capabilities != Benefits
Not every feature translates into value or benefit for the organization. The best feature or tool is the one which suits your current state or level. Organization should select those products that will help them grow to the next level. Organizations cannot make giant leaps forward ahead of competition based on adoption of certain tools, thats a myth.

## Organizing for the cloud

Cloud migration is similar to outsourcing, but has the following advantages:
- Full control
- Transparency
- Short term commitments
- Evolution
- Economics

The cloud manages to draw a precise line between scale optimized implementation and speed optimized business plan. The cloud operating model works best when each team is given end to end control and responsibility over products or functional areas. These are the product teams which cuts across all layers of the system architecture.<br>

**Engineering Productivity Teams**<br>
Teams which maximize the productivity of the product teams by building the common elements of the products such as delivery pipelines or log processing. What they do:
- enable teams to accomplish more
- contribute to customer visible business work
- let the product team still own the development and operations of their product

The Cloud Center of Excellence could be a failure model as they might become a bottleneck for inbound requests and more likely to disable the organization than enable it.

**Retain/Re-Skill/Replace/Retire**<br>
The 4 Rs of people transformation or preparing your workforce for the cloud journey:
- Retain: Your existing developers can easily adapt to the development for the cloud
- Reskill: should be the first option in this transformation to train the existing people on cloud computing.
- Replace: For those people who cannot be reskilled, but this might be required.
- Retire: For those position which are not needed anymore.

Its most likely that your organization already has the people you need for the cloud journey and all they need to be is given an opportunity and re-skilled if required. Create an ecosystem where the best people can contribute their best. Do not re-label, that is give new title names to existing positions/people. 

Its also not a good method to hire a leader from another digital company as they might know the target picture, but not the path leading to it. Instead, look for the following traits-
- Stamina: Someone who has shown the stamina to see a transformation journey from start to end.
- Enterprise experience: Exposure to enterprise systems and environments
- Teacher: They know how to take you where you want to be.
- Engine room: Ability to work in the engine rooms of the enterprise
- Vendor neutral: Look out for candidates who are looking to drive the transformation through product investment alone.

**Enterprise Architecture in the Cloud**<br>
Large enterprises include a team labeled "Enterprise Architecture" as part of the central IT governance. They should focus on the following tasks in an enterprise's cloud journey -
- Inform Business leadership - Separate hype from reality and keep the business leadership informed.
- Link Business, Organizations and IT - Create a holistic view of the architecture and bring all stakeholders together, explaining the why and what.
- Establish guidelines and enable adoption

*Value Delivery Loop*<br>
Developers code -> IT Engineers run software -> Product owners create new features<br>
This loop should spin faster to create value at a fast rate. The EA should work outside the loop and create a two way connection between this loop and other stakeholders such as Business, Cloud Providers and IT Stakeholders.

## Moving to the Cloud

Reasons for moving to the cloud -
- Cost - This can be an advantage only when the elastic pricing is used along with transparency and automation.
- Uptime
- Scalability
- Performance
- Velocity
- Security
- Insight
- Transparency

Organizations should take an application centric view on their cloud strategy, instead of a infrastructure point of view. The application centric view focuses on speeding up software delivery, through increased automation. Carrying the existing processes and systems into the cloud will get you another data center, but not a cloud and that doesn't make a mark.

*Running other's software is a bad deal* due to the following reasons:
- You pay for the hardware
- Installation is cumbersome
- If something breaks, you're guilty until proven innocent
- You can't make changes when you need them

The alternative is Software as a Service where the vendor runs the applications for you.

Consider the following recurring themes in the cloud strategy:
- Onboarding
- Hybrid clouds
- Virtual Private Cloud
- Legacy or Monolithic Applications
- Cost recovery

NIST published a useful definition of cloud computing listed below:
- On demand self-service
- Broad network access
- Resource pooling
- Rapid Elasticity
- Measured Service

A few considerations for Enterprise Cloud:
- Calibrate expectations - Carrying your enterprise baggage to the cloud won't transform anything
- Bring the cloud to you - Bring elements of the cloud operating model to your environment
- Measurable goals - Establish clear goals for the cloud migration and be clear why you are going to the cloud
- Segmentation - Some parts of the applications can go straight to the cloud.

### Phases of Cloud Migration

**Planning and Staffing**<br>
A checklist prior to the migration:
- Size up the migration
- Clarify the motivations and goals
- Define success and metrics
- Get stakeholder buy-in

The following are the critical roles for a cloud migration:
- Executive sponsor - who gets budgets and resources
- Chief Architect - Makes key technology decisions and goals
- Program Manager - handles communication and schedule

Responsibilities of a Program Manager:
- Keeping track of the migration schedule and deliverables
- Applying influence where needed to get the execution going across various teams
- Coordinating the flow of information between various parties
- Publishing regular updates on the migration progress
- Highlighting risks and important decision points to the executive sponsor and chief architect

**Execution**<br>
- Discovery - Gathering information about the existing environment
- Automation and Federation 
    - Automation involves building software to provision, deploy, and verify components in the new environment.
    - Federated Execution - Greater responsibility to individual teams, giving them the freedom on how to deliver the migration outcomes. This won't work for teams that don't manage their own infrastructure
- Training - Teams should be sufficiently trained for the new environment

**Validation**<br>
Classification of validations:
- Environment validation - stress test the environment whether it meets the performance and scale expectations
- Cost validation - Benchmark the actual cost of operations against the projected cost
- Business Goals validation - Validate business goals such as improved security, agility and availability

### Plotting the Execution
The migration can be done in two directions:
- Up - This is same as modernizing the application 
- Out - This is migrating the application or its components to the cloud

The execution or migration should be a combination of both directions. The modernization can occur along multiple dimensions:
- Platform(Iaas -> PaaS --> FaaS)
- Structure(Monolith -> Microservices)
- Deployment(Manual -> Automated)

The decision model of bucketizing for applications -
- Applications that you didn't build(commercial applications)
- Applications that someone built for you(System integrations)
- Applications built in-house

Beware of proxy metrics such as number of applications  or servers migrated. Instead focus on metrics which indicate value. 

## Architecting the Cloud

Difference between multi and hybrid cloud:
- Multi: Running applications on more than one cloud
- Hybrid: Running applications on the cloud and on premise as well and they interact between each other

### Multicloud options

- *Arbitrary*: Applications are deployed to more than one cloud for no real reason.
- *Segmented*: Different clouds are used for different purposes.
- *Choice*: Teams or Business Units have a choice of a cloud provider.
- *Parallel*: Single applications are deployed to multiple clouds.
- *Portable*: Applications are moved across clouds at will.

Deploying the same application across mulitple clouds(Parallel) needs decoupling from the cloud's propreitary managed services:
- Cloud specific functions are isolated from the application as pluggable modules.
- Maintain separate branches of the application for each cloud provider.
- Use open source components which are same across the cloud providers.
- Use a Multi cloud abstraction framework which enables to develop once and deploy to any cloud.

Do note that Hybrid is a required reality, whereas Multi cloud is a choice. Following are the ways to break down a system for a Hybrid cloud:
- Application: Front Tier and Back 
- Application: New Generation and Old
- Application: Non critical and critical
- Application: Dev/Staging Envinronments and Production
- Data classification: Non Sensitive vs Sensitive
- Data classification: Data backup vs Operational
- Operational state: Disaster recover vs Business as usual 
- Workload demand: Burst vs Steady

### Hybrid Implementation strategies

The On Premises is different in the following ways from the Cloud:
- Scale
- Custom hardware
- Diversity
- Bandwidth
- Geographic reach
- Physical access
- Skills

The following are some of the implementation strategies of a Hybrid cloud:
- Define a shared abstraction layer - a uniform run-time and management layer across both environments
- Replicating the cloud environment on your premises(such as AWS Outposts), with either a hardwareor software solution
- Replicating your existing on-premises virtualization environment in the cloud, such as AWS VMWare Cloud
- Building an interface layer on existing on-premises virtualization tools to make it compatible with the cloud management layer; aka control plane

Additional considerations for a Hybrid cloud:
- Identity and Access management
- Monitoring
- Deployment
- Data synchronization

### Avoiding Lock-ins
- Lock-ins aren't binary. Its okay to be locked in to some things to some degree.
- Lock-ins can be avoided with options, but they come at a cost

Shades of Lock-in:
- Vendor
- Product
- Version
- Architecture
- Platform
- Skills
- Legal
- Mental

The cost of reducing lock-ins comes in the following flavors:
- Effort
- Expense
- Under utilization
- Complexity
- New Lock-ins

*The architect’s job to dismantle the buzzwords, identify the real drivers, translate them into an economic/risk model, and then find the best spot for the given business context.*

Cost of Lock-in = Chance of migration * Cost of migration -> This should be measured against the upfront investment required to avoid lock-in. 

With respect to using open source software for avoiding lock-ins, the architects should be aware of the operational costs of the software and getting locked-in with that software which could also be heavily influenced by a vendor. Open source softwares unfortunately allow a lot of abstraction leaks to accommodate for vendor specific constructs.

### Multi Tenancy
Multitenant systems are designed to provide every tenant a dedicated share of a single system instance. The key benefit of such a multitenant system is the speed with which a new share or (logical) customer instance can be created. The key constraints that drive multi tenancy is -
- deploying a new system(for a new tenant) is a complex and time consuming process
- Each new system(for a tenant) will have its stack and needs monitoring

The cloud removes these constraints and easily allows the creation of new systems/instances for every new tenant. This allows to shift to a simpler architecture which could be termed Multi-Single Tenancy. Here the system will exhibit the properties of multi tenancy, but internally will use different instances for different tenants. 

### Disposability
Servers aren't assets and they are a liability. They are expensive, consume a lot of energy and depreciate quickly. Automation allows us to setup new servers fast and easy through scripts which are checked in to source control. This enables us throw away these virtual servers and provision new ones whenever necessary.

Benefits of disposability -
- Consistency - All servers have the same configuration created from the source control, hence no *configuration drift*.
- Transparency - The configuration of the servers are obtained by looking into the source control.
- Less Stress 

## Building for the Cloud

### Application Centric Cloud
To follow an application centric cloud, its important to build a model to characterize the applications living in a cloud. The important characteristics are:
- Delivery pipeline
- Runtime platform
- Monitoring/Operations
- Communication
- Application

The following can be at the intersection of the characteristics in a cloud applications:
- Infrastructure as code/GitOps: Between Delivery pipeline and Runtime platform
- Site Reliability Engineering: Between Runtime platform and Monitoring/Operations
- Service Mesh: Between communications and Monitoring/Operations
- Interface Design Language: Between Communication and Delivery Pipeline

### Containers

Containers combine three important mechanisms that redefine how we deploy and operate applications:
- Artifact packaging
- Image inheritance
- Lightweight virtualization

Benefits of Containers:
- Containers are enclosed
- Containers are uniform
- Containers Stack Tightly
- Containers Load Fast

Some considerations against containers:
- Not everything ships in containers
- Lower levels of isolation
- Containers must be scanned for security

Docker was designed and built for developers, not operations staff. It liberated developers by supporting a DevOps way of working detached from traditional IT operations.

### Serverless

Serverless computing allows you to build and run applications and services without thinking about servers. Server-side logic is run in stateless compute containers that are event-triggered, ephemeral, and fully managed by a third party. Some key points about serverless:
- Stateless
- Compute containers(a self-contained deployment and run-time unit)
- Event triggered
- Ephemeral(disposable)
- Managed by third party
- Auto scales
- Also scales to zero
- Packaged deployment
- Precise billing

Serverless allows us to compare the value (and profit) generated by that function to the cost of executing that function. This is referred as transparent, transaction-level economics, which is a game changer.

### Characteristics of cloud applications

The following list of characteristics is an useful guidance while building applications for the cloud or considering third party libraries for usage:
- Frugal
- Relocatable
- Observable
- Seamlessly updatable
- Internally Secure
- Failure tolerant

### Operations and Resiliency

Systems that don’t break are called robust. Robustness is calculated using MTBF - Mean Time Between Failures. But for an increased uptime, its important to focus on MTTR - Mean Time to Recover. Robustness is usually implemented at the infrastructure level.

Systems that absorb failure are resilient and focus on fast recovery. Resilience generally spans both infrastructure and applications. 

Systems that benefit from failures are antifragile systems. Anti-Fragility spans across the whole system. One approach to building anti-fragile systems is Chaos Engineering - discipline of experimenting on a system in order to build confidence in the system’s capability to withstand turbulent conditions in production. Chaos Monkey is a tool in Chaos Engineering that randomly terminates virtual machine instances and containers. Don't try to be anti-fragile until your systems are resilient.


## Embracing the cloud

The traditional IT hardware is typically two to five times larger than what is actually needed. The migration to the cloud does not yield savings automatically, but they have to be earned by optimization and automation. Optimization is possible because of the transparency provided by the Cloud. Knowing your needs and usage patterns is the most important ingredient into reducing cost.

*Cost[$] = size [units] x time [hours] x unit cost [$/unit/hour]*

The two main levers for costs saving: resource size and lifetime.

Use Automation to spin up infrastracture on failure or when needed, instead of having redundant setups. This automation will yield major savings.

Changing cloud providers does not yield cost savings as they usually *also* involve:
- architecture changes
- pricing model differences

Other considerations:
- Doing nothing - This also could yield savings as cloud providers are constantly reducing unit prices
- Premature Optimization - Not good
- Optimize globally - not just the parts. 

### Run budget

An IT organization’s health is often measured by what percentage of the available budget is spent on operations (“run”) vs. projects (“change”). The spending on the operations is minimized to provide more budget to projects. This spending strategy can be incorrect for a cloud operating model which brings together projects and operations.

False assumptions about cost:
- Invisible cost = No cost
- Recurring costs = Operations
- Visible cost = More cost

Spending on the cloud is a success metric as it indicates higher resources being used to deliver more business value to the clients. The spend and the business value can be computed to the lowest level of usage.

### Automation is not just for Efficiency

Corporate IT celebrating each major product release of its core system to much applause by upper management is a clear sign of
missing build and deployment automation.

Automation must be focused towards the manufacturing parts of software development such as build, test and deployment. This can result in the following benefits:
- Speed
- Repeatability
- Confidence
- Resilience
- Transparency
- Reduced machine cost
- Continuous improvement
- Compliance

### Supermarket effect

When enterprises embark on the cloud journey, they need to get used to a new pricing model that includes more dimensions of charges, such as compute, storage, reserved capacity, network, and API calls. They also need to get used to seemingly minuscule amounts adding up into non-trivial cost. Consider cost management a routine operational task.

Cost may go out of control for the following reasons:
- Self inflicted load spikes(load tests, Internal data migrations)
- Infinite loops(Components calling each other)
- Orphans(Unused resources)
- Shutting down(some dependent resources continue to get used even after shutting down other resources)

Cost can be kept in control with the following ways:
- Set billing alerts
- Run regular scans(to detect underutilized or abandoned resources)
- Monitor higher-level system structures(for detecting infinite loops)
- Manage a new form of error budget(for surprises in billing)












