# Saga_Choreography
Saga Choreography Pattern
This type of asynchronous event-driven saga pattern is used when the code running in each service decides how to handle events in its scope and what to do next. Of course, you can also think of it as a chain of event-driven microservices. Each service listens to the events of others and emits its own events, which can cause events to be paired with each other.

Using the Choreography method will have the best results when more teams are involved in managing the saga. One of the advantages of this method is that each team will focus exclusively on the sagas within its range. On the other hand, there is no need for a separate microservice responsible for coordinating a workflow because there is no central coordinator.

However, this approach can make it difficult to understand more complex workflows and how some services interact. The absence of a central coordinator in the Choreography method has caused the relevant microservices to listen to failure events in order to return to the previous stage.

in this project, Order Service will take an order and the order will be inserted into the database then it will publish a message for the Inventory service to update itself and if the Inventory service failed, the order service will have a compensating transaction to reverse back the order. 
if the Inventory service is successful it will just conclude the transaction.


![saga5](https://github.com/zakizadeh/Saga_Choreography/assets/11499371/c1112f6f-4aa3-4c1c-a609-a0fde5b779d3)


you should run Ecomm Service and OrderService and call Create method of OrderController in OrderService project by Postman.

![saga7](https://github.com/zakizadeh/Saga_Choreography/assets/11499371/6bc8b117-6598-425b-88a8-06150f1e11a7)
