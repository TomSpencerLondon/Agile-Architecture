# Agile Architecture

What does Architecture mean now that software projects are completed with an Agile framework?

### What is Agile?
https://agilemanifesto.org/

The agile Manifesto for Software Development describes four key values and twelve principles
that the authors felt should be used as a guide for software development.

The principles are:
- **Individuals and interactions** over processes and tools
- **Working software** over comprehensive documentation
- **Customer collaboration** over contract negotiation
- **Responding to change** over following a plan

The team value the terms on the right but prefer to give more emphasis to the items in bold on the left.

The team created twelve principles:
1. Satisfy the customer through early and continuous delivery of valuable software
2. Welcome changing requirements even late in the process
3. Deliver working software frequently
4. Business people and developers should work together daily
5. Build projects around motivated individuals - provide the environment but trust them to do the work
6. Face to face converstations are best for conveying information to and within the team
7. Working software is the measure of progress
8. Development should be gradual and constant
9. Focus on technical excellence and good design
10. Keep it simple (avoid doing too much)
11. Self-organizing teams create the best architectures, requirements and designs
12. Regularly check on progress and how to be more effective

### What does Architecture mean?
https://martinfowler.com/ieeeSoftware/whoNeedsArchitect.pdf
- Martin Fowler claims that there is no highest level of system design
- Different people have different views of the architecture
- He suggests a better definition - architecture is the shared understanding of system design
  - the understanding includes how the system is divided into components and how the components interact
- Architecture, according to Fowler, is a "social construct"
- Martin Fowler uses the term Architectus Oryzus (oryza means rice)
  https://web.archive.org/web/20040610210445/http://www.nd.edu/~archives/ooo.htm
  - He also defines the architect as a guide, a more experienced and skillful team member who teaches
    other team members to better fend for themselves and is ready when things get difficult
- He also defines architecture as:
  - "things that people perceive as hard to change"
- According to this definition the practice of agile architecture is ensuring that things are as easy to change as possible
- He agrees with Enrico Zaninotto that "irreversibility" is one of the prime drivers of complexity
- Agile in this reading is the attempt to contain complexity

```text
Software is not limited by physics like buildings are.
It is limited by imagination, by design, by organization.
In short, it is limited by properties of people, not by
properties of the world. "We have met the enemy and he is us."
```

### Agile Architectures
Molly Dishman & Martin Fowler
This is a good video on agile architectures:
https://www.youtube.com/watch?v=VjKYO6DP3fo
- Working Software over documentation
 - doesn't mean working software and no documentation

- Responding to change over having a plan
 - we want something that can change + diagram

Side note: responding to change is an interesting idea here. I particularly like two aspects of this approach.
Firstly empowering teams to make their own decisions on the spot. Secondly the implication that this has for the
role of software developer. The developer is almost trained above their role so that they are more effective at their
job and are able to make better decisions.

https://www.youtube.com/watch?v=6yOPih9zRNs

#### How do we know architecture is happening?
Agile context how stop irreversible things reversible? An agile Approach with Traditional databases. 
Rather than having the database schema defined at the beginning make the database easy to change - series of migrations e.g. split field into different columns
Tools like Liquibase make change reversible so that the database schema no longer hard to change. I am not sure I agree
from what I have seen so far Databases are still quite hard to change. I am interested to explore ideas on how to make them
easier to change.  

Another nexus for change is that of contracts between systems of different systems. 
Ian Robinson writes about consumer driven contracts here:
https://martinfowler.com/articles/consumerDrivenContracts.html

This video is good on consumer driven contracts with Spring:
https://www.youtube.com/watch?v=9cpXaEr3C5o

I have added a repo here which uses consumer contract testing with Spring:
https://github.com/TomSpencerLondon/Consumer-Contract-Testing

During inception (the beginning period of a project) it can also help to agree on what is hard to change
We can also use spikes to explore things hard to change - explore if hard to change or decide later?

Architecture does not lie in artifacts the most important aspect is shared understanding of the team. A good exercise that
Kent Beck used to do was ask colleagues to describe how the system works using 4 objects. Everyone chooses 4 objects. 
If there is no coherence in the objects there is a lack of shared understanding.

Examples in code are good ways of using architecture make sure that good bits are highlighted. We should also collaborate on 
code and change architectural path.

Architects should also book regular times to review code commits and thenpair with less confident commits so that
they can understand what it is happening in the project. In building architects have to keep eye on construction people 
and make sure that plans are carried out and learn from the process.

### Architecture without Architects - Eric Dornenburg
https://www.youtube.com/watch?v=qVyt3qQ_7TA

Eric is talking about Enterprise software development. He claims that using the metaphor of architect is misleading. A better 
metaphor could be town planning. 
As mentioned above, Agile principle 2 refers to:
```text
2. Welcome changing requirements even late in the process
```
In this context it is important to try to minimise the sunk cost fallacy. For instance,
we have spent so much on enterprise service bus we don't want to change it. 
When know something has changed it is not necessary to find fault but rather to do our best at that point in time.

Eric Dornenburg thinks that the gardener like the town planner is better metaphor 
for the Software Architect. Like the gardener the Software Architect tends to software components (plants) 
and weed out and decommission irrelevant elements of the architecture. So Conclusion 1 is that 
Architecture is a tricky and even dangerous metaphor.

#### Can something complex evolve?
Eric Dornenburg defines evolution as:
• recombination
• mutation
• fitness function - compare and select success

#### Vertical slicing
- best way to tell if architecture is working - one team end to end
- agile development - story from end to end

Often architects focus on Querschnittsfunktionen - cross functional requirements - this should be in the background
We should rather focus on vertical slices as ways of exploring ideas and architecture of the system.

So the definition of the architecture is the stuff that expert developers find important to describe the system
is gradually changing over time to the point where the origins are no longer discernable.
Starting points can include:
- How much upfront design is possible?
- How much upfront design is reasonable?
- What does "upfront" even mean? 
  - is it upfront for the entire system or for individual components

#### Architecture is mostly an ongoing activity
The seductive power of abstractions
- common infrastructure frameworks
- Developers do need to know what is beneath the abstractions

#### Architecture and Development can't be separated
- design diagrams and models
- patterns
- frameworks
- Architects should write code
- Tests are also important
- Guidelines / principles
- Visualisations

#### Architecture principles
- Composition over inheritance
- Code should be one deployable
- new instanceof an old one must be removed
- Every deployable has health page providing information about configuration + state in a text based format


### Designing for Performance
Martin Thompson
- Good video on designing for performance:
https://www.youtube.com/watch?v=03GsLxVdVzU

Is it difficult writing software that has good performance?
https://www.semiconductors.org/wp-content/uploads/2018/06/0_2015-ITRS-2.0-Executive-Report-1.pdf
We are burning alot of energy and heat with data centres.

#### How do we design for performance?
1. What is Performance?
2. What is Clean and Representative?
3. Implementing efficient Models
4. Why Performance Test?

We can think of performance as Throughput (aka Bandwith). It is also to consider Response Time (aka Latency).
Increasing Throughput can affect Response Time. We should also consider Scalability. If we scale we should consider whether
this will affect Response Time. Queueing theory is important for performance. What is the response time, latency, cycle time?
The major things that matter are the service time. How long does it take to get service at the front of the queue.
Response time is wait time + service time. As we increase load on a system the response time goes down.

#### Queueing Theory
![image](https://user-images.githubusercontent.com/27693622/230115660-623bd7ba-0a79-4381-9283-b4b116300c86.png)

While the utilisation is at 50%, when you get to 70% utilisation response time gets bad very quickly. We need to reduce the
cycle time and service time to improve response time. Making the service twice as fast can reduce the utilisation and have 
large effects on the response time.

#### Can we go parallel to speedup?
It depends on what we parallelise.
![image](https://user-images.githubusercontent.com/27693622/230116875-a39266ff-302c-4d8f-b5c6-67fd407435ee.png)

Going parallel at 50% doesn't give huge improvements:
![image](https://user-images.githubusercontent.com/27693622/230117135-1febde56-6628-4ec5-b2bf-ba37c17864c3.png)

![image](https://user-images.githubusercontent.com/27693622/230117434-4b389a4d-e9fc-4d69-8cd3-658cf777e1e7.png)

Everything takes time when we increase the number of processors. 

![image](https://user-images.githubusercontent.com/27693622/230117790-dc65dcfc-f847-4c3d-aa0e-afda85d3459b.png)

The coherence penalty can greatly affect the advantages of parallelisation. This graph of threads means that two threads
make things work even harder:
![image](https://user-images.githubusercontent.com/27693622/230118296-8f5dfc5a-2132-454c-a579-bbeeb24f7097.png)

The above describes our logging frameworks. All logging frameworks suffer from the same issue. They are very ineffecient.

#### Clean & Representative
- clean = "Morally uncontaminated; pure; innocent"
- representative = "serves as a portrayal or symbol of something"
- Code is the best place to capture our current understanding of the model
- Clean simple code is often the most performant code

#### Abstractions
1. Don't use abstraction
2. Don't use abstraction
3. Only abstract when we have 3 things that are the same
4. Abstractions must pay for themselves
5. Beware DRY => often leads to abstraction and coupling
   - only abstract after you see duplication

Abstraction can cause issues with performance. If the code is not representative then it can be a code smell.
Usually we should say no to big frameworks. There is only a certain amount of things we really need. The less code we have
the easier it is to reason about and the more performant it is.

```text
All non-trivial abstractions are to some extent leaky.
The detail of underlying complexity cannot be ignored. 
```
Joel Spolsky

```text
... the purpose of abstracting is not to be vague but to create
a new semantic level in which one can be absolutely precise.
```
Djikstra


#### How hardware software reacts to our code
1. The temporal bet
2. The spatial bet (cohesiveness)
3. The pattern bet (expect access in certain ways)

#### Coupling and Cohesion
We should practice coupling and cohesion everyday. Many objects are just properties bags. Feature envy is when
one object is envious of the fields in another object. When we get coupling and cohesion correct things will be
spatially and temporally together. Just going through coupling and cohesion can increase throughput and response time.
We should respect the locality of reference. The cache is a critical part of how our hardware works so it must be respected.

Can you implement a B+ Tree efficiently in your language?
This video is quite good on B+ trees:
https://www.youtube.com/watch?v=_XwsETNHf8c
https://www.cs.usfca.edu/~galles/visualization/BTree.html
As we use access memory we need blocks. 
This is a Bplus tree implementation in Java:
https://github.com/shandysulen/B-Plus-Tree

#### Relationships
We need relationships to work well between objects. Take the time to understand relationships:
![image](https://user-images.githubusercontent.com/27693622/230129731-38e3a85b-5fb3-4f0d-9b7a-822f042e88b7.png)

Get back to studying data structures and learn more about them. Data structures are the fundamental building blocks of good code.

#### Batching
The key to batching is amortising the expensive costs.
![image](https://user-images.githubusercontent.com/27693622/230130335-232888d7-f38e-4baa-aeea-95d3e69f65be.png)

Building systems with batching allow us to reduce increases in response time:
![image](https://user-images.githubusercontent.com/27693622/230130556-e52c4298-5478-41bc-9384-340db4de94fd.png)

#### Branches, branches, branches...
Branching of code can be very expensive. 

![image](https://user-images.githubusercontent.com/27693622/230131271-540b3740-e456-44d4-91b6-53bf789ef7e7.png)

In the above example it is better not to use the if statement. Respect the principle of least surprise.

#### Loops
```text
if I had more time, I would have written a shorter letter.
```
Blaise Pascal

Allow time to complete work and then go back to the work to review the code. Behind level one cache we have a Level 0 cache.
Keeping loops small and elegant can help working with the cache. Keeping simple helps the hardware.

#### Composition
Size should be as small as possible as this helps reusing classes. Single Responsibility is important. Small atoms can be composed effectively.

#### APIs
APIs are incredibly important. This is NIO code:
![image](https://user-images.githubusercontent.com/27693622/230133468-434e4b6f-2cf9-4a8b-8f21-0660e9346112.png)

This code is better:
![image](https://user-images.githubusercontent.com/27693622/230133772-078970cd-b1f0-49fe-9139-89d792e62e9b.png)

Enable the caller to choose.

#### Data
How do we deal with filtering searching and finding data. Rather than collection of objects think of collection of arrays.
We can then do vectorisation. Think in columns as well as rows.
Embrace Set Theory and Functional Programming Techniques.
This is good on performance improvement:
https://richardstartin.github.io/posts/5-java-mundane-performance-tricks
EnumMap is better than just Map:
https://www.geeksforgeeks.org/enummap-class-java-example/
https://blog.jooq.org/top-10-easy-performance-optimisations-in-java/


#### Define Performance goals

#### Measure Response time
Don't just measure service time.



Microbenchmark harness:
https://www.baeldung.com/java-microbenchmark-harness

Aeron systemcounters:
https://github.com/real-logic/aeron
count:
- queue lengths
- concurrent users
- exceptions
- transactions - orders, trades

### Other Definitions of agile processes
### Digital Service Manual
https://www.youtube.com/playlist?app=desktop&list=PL5tovFCB3CsAFicGXOSHZiF-FjIMb3Zfd

Four phases of design:
1. Discovery (requirements gathering)
2. Alpha (first attempt)
3. Beta (more robust)
4. Live (fully functioning)

#### 1. Discovery
- Scoping
- What does a good service look like?
- Read a lot of information
- Familiarise with knowns and unknowns
- 3 / 4 weeks
  - research
  - series of workshops
  - who are the users, what do they need
  - How would we develop the service
  - Shared buy in
  - How to measure success
  - people for building Alpha
  - Ask "Why?"

#### 2. Alpha
- Opportunity to show team and stakeholders how the application will work
- When describing and explaining
  - Alpha will enable feedback on the solution
  - fail fast and make the application better
- End of alpha may lead to working website
  - buy in
  - user testing for next stage
  - not finished if there is conflict in the room
  - Build quickly and collaboratively

#### 3. Beta phase
- starting to make the product real
- security, data retention
- Alpha = proof of concept
- Beta = security and performance affect results

#### Agile
- not waterfall - traditional gather requirements + deliver and test
- instead of waiting for the end of the process, do a bit of all processes each week
- what we are building is constantly getting improved
  - end result is product of iteration and improvement
- product grows and evolves over time

### User research
- Understand what the user wants and what we think they want
- Insights to inform design and development of products and services
- Ethnographic research - see how users use the site
- Usability testing
- Get to know the users, be clear on where product is in lifecycle, get the team involved with research
- collaboration is fun
- Good at listening
- Empathy - see things from users point of view

#### What is a delivery manager?
- look after the development team
- huddle the developers
- check if developers have blockers
- everyone should know what everyone is up to
- Delivery manager - make sure the thing happens - how not why
- Product manager is about the Why - whether they have the right product

#### What does a developer do?
- works on code for the project
- build the tools and programs
- work with content designers to produce the end product
- decide on architecture of the project
- check on user testing
- need team ready to work together

#### Designer
- site between developers and product owners
- see how the product works - lab based user testing
- work with stakeholders and users
- should not be afraid to question the brief and understand constraints of the technology

#### Service Manager
- someone prepared to take responsibility from start to end
- dedicated to learning the system to pre-empt issues
- good communication skills
- gain respect from your colleagues - know service from back to front

#### What is performance analysis
- Google trend reports - trends in usage
- increase in search terms
- not just spew out reports - analyse trends and actions to improve things
- measurable improvements
- what the users are doing - pychological aspect of how user interacts with the application
- User research all the time
- Comments on each government page
- Try to provide service to citizens - make the service better and learn from mistakes

#### Assisted Digital and the Digital Service Lifecycle
- What proportion of the user base do we think will be able to use the service independently?
- Plug gaps during the Alpha phase
- Discovery phase find out what information we need
- End of the Alpha phase => understand options for what support will look like
- Live: service standard 26 criteria - expect digital support to be live

#### What is assisted digital?
- 18% of population who haven't used the internet or have low digital skills
- Those people who can work out how to fill in forms
- Make sure services are available and people are there to help
- focused on helping people to use digital services


#### Nick Stenning What does web ops mean?
- Web operations provide the infrastructure
- system administrators and developer skills for collaborating to build working applications
- Skills: 
  - ability to solve problems, scientific mind, monitoring and use the information to fix performance
  - confidence to compose research into new solutoins

### CTO Digital Service (Liam Maxwell)
- Identify how best to implement new technology problems
- Digital Service Manual is there to help people find the best solutions
- Be transparent and open about the numbers
  - collaborate and work with people
  - more sharing for better solutions

#### IT reform strategy
- Not providing colleagues in software services best tools
- Decouple services applications and middleware
- operating model to think of different suppliers for diffferent aspects of service
- security: simple, transparent and complete
- open standards maintain the ability to take advantage of best market can provide

#### Content Designer
- web editor - not just what tell people but what people want to know
- user does not need to read it properly - it is simple and efficient in communicating knowledge
- most users are not browsing - they want to be able to do something
- sometimes short amount of time to make changes for nationally important information
- sculpt language to make it as simple as possible and efficient

#### Technical Architect
- role of architect changes during the different stages of the development project
- Technical architects should be able to work with developers
- Go to meetings and understand business
- convince people
- is the team working well?
- working on a project, to working on a product, to working on a platform
- experience is helpful - see more things and sense what will happen next

#### The stages of agile delivery
- Discovery (exploring the problem)
- Alpha (testing options with hypotheses)
- Beta (building and refining options)
- Live (continuously improving)