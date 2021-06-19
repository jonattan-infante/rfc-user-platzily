- Start Date: (19-06-2021)

# RFC User Service

## Summary

>  Architecture design about the new User Service that will be release soon for the new development of Platzily


## Motivation

#### Why are we doing this? 

Because we want to learn to develop projects made up of several development teams that work sharing information and services and at the same time being independent. Applying architecture design tools such as the **C4 Model** and the **CAP Theorem** to visualize the layers, interactions, information flows and land the business logic in technologies.

####  What use cases does it support? 

The following use cases will be supported:
-   Flow user creation.
    -   Create account.
    -   Validate account.
-  Links management.
-  Campaign management.
-  Create web client(UI) for users service.

####  What is the expected outcome? 

Offer a functional service, consistent and independent service from other services that can be consumed by other dependencies of platzily.

## Design Detail

User service is limited by a domain that includes the **user** and **campaigns** entities, as well as the use cases that these entities may have with external services such as the creation of links by a user and the possibility of associating a link to an already created campaign.

				Diagram Domain
![Diagrama de Dominio](https://res.cloudinary.com/dahid6yzj/image/upload/v1623981385/platzily/diagrama1.jpg)

The user architecture in a global vision will be composed of a Single Page App that will be in charge of delivering the necessary UI for the user to access the registration and login flow to later redirect it to their management dashboard.

The functionalities for the Single Page App will be supported by an API that will store and consult the information about the users from a database of the user service environment. However, to create links and associate them with a campaign, external services such as **Statistics**, **Core** and **Link** will be used.

				Layer 2 diagram of the C4 Model
![enter image description here](https://res.cloudinary.com/dahid6yzj/image/upload/v1624064175/platzily/c2.png)								


				Layer 3 diagram of the C4 Model
![enter image description here](https://res.cloudinary.com/dahid6yzj/image/upload/v1624063759/platzily/c3.png)

### Flows
![enter image description here](https://res.cloudinary.com/dahid6yzj/image/upload/c_scale,w_577/v1623987987/platzily/sequence1.png)
![enter image description here](https://res.cloudinary.com/dahid6yzj/image/upload/c_scale,w_577/v1624061530/platzily/secuencia2.png)

## Rationale and Alternatives

### What is the impact of not doing this?

Without a user system, it would not be possible to manage statistics, manage campaigns and links.

## Unresolved questions

###  What related issues do you consider out of scope for this RFC that could be addressed in the future independently of the solution that comes out of this RFC?

This RFC does not address campaign creation and user authentication.
