---
layout: post
title: Cloud Computing
published: true
category: cs 
---

You might have a splendid idea of developing a web/mobile aplication that you think will be a hit for the next decade. Thus you will need to think of deploying it on servers with enough resources to be able manage the load of people turning in. However, buying servers on your own might cost you an arm and a leg,  and you probably won't use all the resources day and night. Plus you will likely be in need of hiring people that will be in charge of maintaining the servers in a good shape in times of influx uptick.  

The cheapest and efficient way for you and probably most of small or even big companies is to rent third-party servers and be charged depending on the duration of usage. This solution is know as __cloud computing__. 

### What is cloud computing? 
<img src="https://assets.intersystems.com/dims4/default/12febb9/2147483647/strip/true/crop/780x422+0+0/resize/1560x844!/format/webp/quality/90/?url=http%3A%2F%2Finter-systems-brightspot.s3.amazonaws.com%2F26%2Fbd%2F6a6aa762425f87ad7d5c2fe65f8c%2Fawslogo-image.jpg" alt="aws"/>

Cloud computing is the delivery of computing services—including servers, storage, databases, networking, software, analytics, and intelligence—over the Internet (“the cloud”) to offer faster innovation, flexible resources, and economies of scale. 

### Cloud computing models
There are different models of cloud computing that pertain to the infrascture environment as well as the type of service you can benefit from. 

##### Deployment models 


These models pertain to where the infrastructure environment is located. There are mainly 3 types:

<img src="https://images.prismic.io/superpupertest/b6d7eacb-98bd-4bed-b811-603ee89daef7_Frame+1978.jpg?auto=compress,format" alt="depModels"/>


__Public Cloud__: It refers to computing services offered by third-party providers over the public internet, making them available to anyone who wants to use or purchase them (e.g.: Azure, AWS, ...).

This is probably the most straight-forward solution if you are sure your application is not using sensitive information that might hacked by potential adversaries.

__Private Cloud__: It refers to a model of cloud comouting where IT services are provisioned over private IT infrastructure for the dedicated use of a single organisation. 

This usually used by organizations manipulating sensitive data like hospitals, intellegence agencies, ... . 

__Hybrid Cloud__: A cloud computing environment that uses a mix of on-premises, private cloud and thrid-party, public cloud services with orchestration between the two platforms. 

This can be the example of a private research company whose marketing application through which anyone can sign up/in can be hosted on a public cloud, however all the research matters (which are likely sensitive) are hosted on a separate private cloud. 

##### Cloud service models 

These are models relate to the general architecture provided to users. We can distinguish between 3 types:
<img src="https://www.stackscale.com/wp-content/uploads/2020/04/cloud-service-models-iaas-paas-saas-stackscale.jpg
" alt="servModels"/>

__Infrastructure as a service (IaaS)__: refers to providing complete access to the server's OS. Typically, IaaS provides hardware, storage, servers and data center space. However, it is up to the user to get their own solution (e.g. application) up and running on the cloud (by making the necessary installements, uploading website files, ...). 

__Platform as a service (PaaS)__: one does not get access tot he whole OS. Rather access is given at a Dashboard level, where a user uploads data, and the rest is taken care of by the cloud provider. In other words, this is the automatic version of IaaS. 

Imagine you have a website ready to be deployed but you don't want to go through all the steps of installing necessary deployment apps (e.g. Apache) on the server, ... In this case, you use PaaS and the cloud provider will be in charge of doing this for you. The only thing left for you is to upload the website files, ...

__Software as a service__: refers to the practice of directly providing the software to the customer, without making any server or dashboard available for them, e.g.: Google Drive, Facebook, ...

In case of Netflix for instance, you only benefit from the software for your monthly subscription, without having at hand any server, or dashboard. 

In the sequel, we will only interest ourselves with the __AWS__ cloud provider, since it is by far the most largely used cloud provider in the world in which even big tech companies deploy their apps (e.g. Netflix, Airbnd). 

### Service domains in AWS 
AWS offers a large panel of services that cover the following areas:
* Compute
* Storage
* Database
* Security
* Management
* Customer Engagement
* App Integration ...


