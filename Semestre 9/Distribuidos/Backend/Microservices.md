Monolithic:
- Modelo Vista Controlador
- Client-Server

SOA (Service Oriented Architecture)
Divides the monolithic

Ejemplo:
- Payments
- CRM (Customer R Manager)
- ERP (Enterprise Resource People)

Microservices:
Even more divisions of SOA

- Payments turn into:
	- Providers
	- Payroll

Theyre agnostic. Like its part of the system, but its independent of the system
Every microservice can work by itself and can work in various systems

Theyre small and autonomous. 
They do one single thing

Every service is designed to communicate through HTTP or REST

Features of microservices:
- Independency - Development, deployment, and maintenance
- Modularity - Update, and removal of services without impacting the system
	- This is mostly in theory. Its possible, but if we delete a core microservice it will actually affect the system
- Scalability - Individual scaling based on needs, resource efficiency
	-  Serverless (wont be deployed on a server, theyre on AWS lambda)
	- Containers
- Communication - HTTP/REST or messaging (queues - Kafka)
	- Kafka does asynchronous requests.
		- When we make a request, we dont need the response immediatly
	- Rabbit MO
	- Artemis MO
	- SOS (AWS)


Aeromexico example:
- Checkin
- Payment
- Ancilaries

Every request consumes CPU and RAM. So we can make it scale it, through events, requests, or an umbral of resources.
We can scale the microservices depending on the amount of services required, or the resources available


For small systems, Monolithic is better. The communication is simpler. Its easier to program. Easier to deploy, since we only need to do it once. 
Theyre hard to change, hard to scale. 

Microservices are easy scalable. We can create different services on parallel, one team does the payment, other does the checkin, etc. We dont need to scale the whole system, we only change one microservice.
Resilience, if one microservice fails, the whole system wont be affected.
It has tech flexibility. Every microservice can be written in different languages. Since the communication is done through HTTP/REST.

Since every microservice is done in different technologies, its very complex to manage.
Microservice communication is difficult.
Deployment is more complex
Data consistency.
Observability 

CI/CD - Continuous Integration/Continuous Delivery

# Patterns

- API Gateway - Most used
	- One single entrance for our microservices. This API decides which microservice it will route on (like a router with firewall)
	- AWS API GW
- Circuit Braker
- Saga Pattern

