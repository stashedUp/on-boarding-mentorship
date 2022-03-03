## Project Two

For this project, you will need to implement a microservice architecture. 

You will use:
* ECS Fargate
* RDS Database <!-- or dynamo -->
* ALB

The goal of this project is to: 
* Create a bigger architecture with end to end process
* Use a database should handle CRUD operation
* Observe how scaling works with an ALB
* Learn the how to use internal vs external network work

At the end of this project you should be able to answer the following questions:
* Can your application scale with 1 million users concurrently?
* How would you measure the latency of your application?
* Are you handling high availability? Do you have redundancy for your databases?

#### Project description
Create an application that will that will register an astronaut and their hours that they have logged. In your Project Two folder, you will find the necessary files and instruction to architect this infrastucture. 

When a user (astonaut) visits your application, they will be presented with a view to log their training hours.
1. First, create a signup page.
1. After the user logs in, he/she would be able to log their hours.
1. On another tab, they would be able to see everyone's logged hour.

| Name      | Hours |
| ----------- | ----------- |
| Buzz      | 102       |
| Neil   | 111        |
| Collins   | 100        |
| Musk   | 2        |

### Monolithic apps in comparison to a microservices architecture.

There are times during the initial stages of the business when teams chose to move forward with the monolithic architecture & then later intend to branch out into the distributed, microservices architecture.

Well, this decision has several trade-offs. And there is no standard solution to this.

In the present computing landscape, the applications are being built & deployed on the cloud. A wise decision would be to pick the loosely coupled stateless microservices architecture right from the start if you expect things to grow at quite a pace in the future.

Because re-writing stuff has its costs. Stripping down things in a tightly coupled architecture & re-writing stuff demands a lot of resources & time.

On the flip side, if your requirements are simple why bother writing a microservices architecture? Running different modules in conjunction with each other isn’t a walk in the park.

#### Discuss with your mentor the pros & cons of a Monolithic architecture  

### What Is A Microservices Architecture? #
In a microservices architecture, different features/tasks are split into separate respective modules/codebases which work in conjunction with each other forming a large service as a whole.

Remember the Single Responsibility & the Separation of Concerns principles? Both the principles are applied in a microservices architecture.

This particular architecture facilitates easier & cleaner app maintenance, feature development, testing & deployment in comparison to a monolithic architecture.

Imagine accommodating every feature in a single repository. How complex things would be? It would be a maintenance nightmare.

Also, since the project is large, it is expected to be managed by several different teams. When modules are separate, they can be assigned to respective teams with minimum fuss, smoothening out the development process.

And did I bring up scalability? To scale, we need to split things up. We need to scale out when we can’t scale up further. Microservices architecture is inherently designed to scale.

The diagram below represents a microservices architecture:

<img src="../readme_files/micro.jpeg" width="440"/>   

Every service ideally has a separate database, there are no single points of failure & system bottlenecks.(But we won't do that for this project)

#### Discuss with your mentor the pros & cons of a Microservice architecture  



Resources: 
- 8bitmen.com
- https://www.educative.io/
- https://blog.logrocket.com/creating-a-web-server-with-golang/