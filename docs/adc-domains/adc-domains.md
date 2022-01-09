# ADC Bounded Contexts & Domains

The ADC (**_AnyChain Digital Custodian_**) implementation is based on Domain-Driven Design ([DDD](https://en.wikipedia.org/wiki/Domain-driven_design)) and implemented as a set of serverless design patterns. Our solution is focused purely on the individual functions defined within our structured domain model. ﻿ Our frontend uses autonomous microapps that are independently deployed. The objective of a micro frontend is to divide the user experience into a set of independent micro applications, while also providing users with a seamless experience.


![alt_text](image1.png "image_tooltip")


DDD defines a separate domain model for each subdomain. A subdomain is a part of the _domain_, DDD’s term for the application’s problem space.

DDD calls the scope of a domain model a _bounded context_. A bounded context includes the code artifacts that implement the model. When using the serverless architecture, each bounded context is a set of self-contained services.

The DDD concept of subdomains and bounded contexts maps nicely as a set of serverless design patterns. Our solution is focused purely on the individual serverless functions defined within our subdomains.﻿ Our frontend uses autonomous microapps that are independently deployed. The objective of a micro frontend is to divide the user experience into a set of independent micro applications, while also providing users with a seamless experience.

DC UI Bounded Context & Domain

The AnyChain mobile or web user interface is not monolithic. The frontend is to be implemented using autonomous microapps that are independently deployed. The objective of a micro frontend is to divide the user experience into a set of independent micro applications, while also providing users with a seamless experience. The main entry point will act as a metadata-driven assembly and menu system. This approach breaks the presentation tier into a set of independently deployable micro applications but stitches them back together for a seamless UX. As users move between different activities, it will not feel like they are jumping between applications. It feels like a single application.

The **_DC UI_** is the standard AnyChain microapps implementation and the Owner’s primary interface to ADC.  It is a mobile application with built-in core functionality for creating an ADC account, authenticating an Owner as required and securing/backing up critical private keys/data. The DC UI also supports microapps that may be dynamically added as required to support desired functionality. Examples of microapps include an Owner’s feed, content creation, owner



DC Identity (DCI) Bounded Contexts

The DC Identity (DCI) Bounded Context contains these Domains:



* DCI-Identity Broker
* DCI-Persistent Storage
* DCI-Owner Events



DCI-Identity Broker Domain


![alt_text](image2.png "image_tooltip")


DCI only supports a single Owner and binds to their mobile device. DCI becomes the Owner’s proxy online by performing all actions on the Owner’s behalf at their direction.

DCI-Persistent Storage Domain


![alt_text](image3.png "image_tooltip")


DCI Persistent Storage is where all of an Owner’s important data is stored besides their private keys and other protected data contained in their Protean Credential. The primary goal here is to provide a secure key value storage location under the Owner’s control.

DCI-Owner Events Domain


![alt_text](image4.png "image_tooltip")


DCI Owner Events revolves around the Owner’s Queue of events and how those events are processed and managed. These events encompass activities that require automation (e.g. process a subscription), drive Owner behavior (e.g. specify microapps for the UI) and provide content for the Owner to engage with (e.g. audio, video, messages, etc.).

AnyChain (ACC) Bounded Contexts

The AnyChain Cloud (ACC) contains these Bounded Contexts and Domains:



* Cloud
    * ACC-Admin
    * ACC-Auth
    * ACC-Connections
    * ACC-Content
    * ACC-External Services
    * ACC-GuestBook
    * ACC-Vault
    * ACC-Wallet
* Storage
    * ACC-Storage
* Guides
    * ACC-Composer



ACC-Admin Domain


![alt_text](image5.png "image_tooltip")


ACC-Admin is focused on Owner and cloud administration. This is where ACC is configured and admins/Owners can personalize their environments.

ACC-Auth


![alt_text](image6.png "image_tooltip")


ACC-Auth is used to enroll and authenticate Owners. This domain creates the Protean Credentials Owners used to access their ADC environment.

ACC-Connections


![alt_text](image7.png "image_tooltip")


ACC-Connections is how Owners connect with others and manage those connections through their lifecycle (e.g. key rotations).

ACC-Content


![alt_text](image8.png "image_tooltip")


ACC-Content supports organizing and sharing content with an Owner’s connections. This domain packages content into Blocks (encrypted archives) that are shared over IPFS.

ACC-External Services

ACC-External Services is where serverless functions representing APIs for an external blockchain or service are found. This domain is how blockchain activities like sending or receiving value are integrated into ADC. These serverless functions will require supporting infrastructure like blockchain nodes which should be deployed in the ACC environment.



ACC-GuestBook


![alt_text](image9.png "image_tooltip")


ACC-Guestbook is designed for controlling access to public profiles, supporting Owner discovery and logging visitor activity.

ACC-Vault


![alt_text](image10.png "image_tooltip")


ACC-Vault provides secure encrypted storage of Owners important credential data (e.g. private keys for wallets). It is a backup service where only authorized Owners can recover their keys.

ACC-Wallet



![alt_text](image11.png "image_tooltip")


ACC-Wallet controls payment activities on an Owner’s behalf. Owners may create wallets for supported blockchains and ACC-Wallet enables automation (e.g. subscription processing) as desired.

ACC-Storage


![alt_text](image12.png "image_tooltip")


ACC-Storage manages object storage for Owners while sharing desired Blocks over IPFS.

ACC-Composer


![alt_text](image13.png "image_tooltip")


ACC-Composer is where serverless functions and blueprints become ADC activities and guides. It is also how ADC may be extended to support additional external systems.
