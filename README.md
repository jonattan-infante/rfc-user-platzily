- Start Date: (19-06-2021)

# RFC User Service

## Summary

>  Architecture design about the new User Service that will be release soon for the new development of Platzily


## Motivation

#### Why are we doing this? 

Because we want to learn to develop projects made up of several development teams that work sharing information and services and at the same time being independent. Applying architecture design tools such as the ** C4 Model ** and the ** CAP Theorem ** to visualize the layers, interactions, information flows and land the business logic in technologies.

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

User service is limited by a domain that includes the ** user ** and ** campaigns ** entities, as well as the use cases that these entities may have with external services such as the creation of links by a user and the possibility of associating a link to an already created campaign.

				Layer 1 diagram of the C4 Model
![Diagrama de Dominio](https://res.cloudinary.com/dahid6yzj/image/upload/v1623981385/platzily/diagrama1.jpg)

The user architecture in a global vision will be composed of a Single Page App that will be in charge of delivering the necessary UI for the user to access the registration and login flow to later redirect it to their management dashboard.

The functionalities for the Single Page App will be supported by an API that will store and consult the information about the users from a database of the user service environment. However, to create links and associate them with a campaign, external services such as ** Statistics **, ** Core ** and ** Link ** will be used.

				Layer 2 diagram of the C4 Model
![enter image description here](https://res.cloudinary.com/dahid6yzj/image/upload/c_scale,w_577/v1623982530/platzily/c1.jpg)								


				Layer 3 diagram of the C4 Model
![enter image description here](https://res.cloudinary.com/dahid6yzj/image/upload/v1623988884/platzily/c3.jpg)
![enter image description here](https://res.cloudinary.com/dahid6yzj/image/upload/v1623987987/platzily/sequence1.png)
![enter image description here](https://res.cloudinary.com/dahid6yzj/image/upload/v1624061530/platzily/secuencia2.png)

## Drawbacks

> Why should we *not* do this? Please consider the impact on users,
on the integration of this change with other existing and planned features etc.

> There are tradeoffs to choosing any path, please attempt to identify them here.
> Consistencia y disponibilidad

## Rationale and Alternatives

> Why is this design the best in the space of possible designs?

> What other designs have been considered and what is the rationale for not choosing them?

> What is the impact of not doing this?

Sin un sistema de usuarios, no seria posible manejar estadisticas, administrar las campañas y links. 



## Prior Art

Discuss prior art, both the good and the bad, in relation to this proposal. A few examples of what this can include are:

> How other services / infrastructures in the same domain have solved this problem.

> Are there any published papers or great posts that discuss this? If you have some relevant papers to refer to, this can serve as a more detailed theoretical background.

This section is intended to encourage you as an author to think about the lessons from other organisations, provide readers of your RFC with a fuller picture. If there is no prior art, that is fine - your ideas are interesting whether they are brand new or if it is an adaptation from other services.

## Unresolved questions

> What parts of the design do you expect to resolve through the RFC process before this gets merged?

> What parts of the design do you expect to resolve through the implementation of this feature before stabilisation?

> What related issues do you consider out of scope for this RFC that could be addressed in the future independently of the solution that comes out of this RFC?

No resolvemos creación de campañas, autenticación de los usuarios. 
