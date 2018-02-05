# Google Cloud Platform Training - 26/01/2018

[Google Cloud](https://cloud.google.com)
## ToDos

* Lookup GCP SRE (Google Cloud Platform - Site Reliability Engineering)
  * This is more infrastructure related, (probably not interested)
  * Things will fail, you deisgn to make coming accross failure easy.

## General Notes
Projects have their own boundaries. Creating a virutal machine is the first building
block(the foundation) for gcp.

GCE is the google copute enginge and is where you go to create a virtual machine.

**What are zones?**
Zones are datacenters. Locations can have many different zones, meaning one
location hcan have multiple datacenters. You should put your datacenters as
clsoe to your custoemrs as possible.

Google seems to be running their own cables. They have their **own global networks** that
connects all of their data centers. This makes their connections predictable and also
makes their latency lower.

Google handles networking to the best of their ability. And this is what you
gain with using their platform. This is the core of why you would choose the GCP
over something like heroku, aws and digital ocean. The google network is all about
**predictable performance**.

It's easy for google vms to talk to each other.

Google Cloud Launcher is what allows you to deploy preconfigured vm instances.
Some of these instances require you to pay for licensing instead of license stack.


##Deployment Manager
This allows you to have a base image to build different machines. This allows you
to rebuild machines from the base.

##GCP Computer Architectures

* Compute Engine
  * Raw computing power
* Kubernetes Engine
  * Container Management System
* App Engine
  * Is supposedly going to charge you as your card goes. You don't have
  much control over app engine and it doesn't need to have the probabilty.

* Cloud Functions
  * This is where you will have your nodejs scripts run
* Managed Services

Google has tons of CDNs across the globe. _View them as on-ramps to the zones_

## Security Tips

Seperate your duties with roles, if something bad goes in, you know that groups of
accounts had to work together to accopmlish this goal. This way if all of the actors
are involved.

## Cloud Functions & Cloud Endpoints

Cloud Functions use NodeJS while Cloud Endpoints allows you to use anything you want

## IaaS & PaaS

Kubernetes engine allows you to run your containers

## Cloud Storage
