---
layout: post
title:  "PCF"
date:   2020-11-23 22:25:00 +1000
categories: Geek
---

Why do we need PCF if the Docker and Kubenettes can serve most of the scenario?

PCF is high level abstraction compared with K8s, it let the developers focus on the application itself, and don't need to worry about the low level configuration (e.g. runtime), but the drawback is it use the felxibility as the trade off.

How to use that on deployment?

We can use the cli `cf push`, either the flag or the manifest.yaml file to specify the deployment detail.

How to use that for logging?

We can use cli `cf log APP_NAME`, or any other equivalent GUI like `Apps Manager`, but as the Pivotal Web Service has been EOA, you can only use the self-hosted one now.

How to do the auto scaling?

Same thing, use cli or `Apps Manager`.

Verdict:

From Jan 2021, there's no PCF anymore, Pivotal has been fold into VMWare Tanzu project, and PCF has been rename to Tanzu Application Service (TAS) and their PaAS Pivotal Web Service has been terminated as well.

To use TAS, we can need to do the self hosted, but luckily enough, AWS provide the [built-in template](https://aws.amazon.com/quickstart/architecture/pivotal-cloud-foundry/) to quick start the TAS, which will help you to create all the thing you need in TAS, e.g. ELB, Tanzu instance, S3 bucket for build pack etc.  

But in the context of rising DevOps culture, PCF/TAS is designed to let the developer focus on coding, and simplify the deployment and scaling, but the abstraction trade off the flexibility. From my point of view, it's not worthy.

So I would say I prefer the K8s or docker eco system.