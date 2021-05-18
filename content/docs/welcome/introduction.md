---
title: "Introduction"
description: "Welcome to the FakeCo API Documentation site. This is your 1 stop shop for all things related to the FakeCo APis."
date: 2020-10-06T08:48:57+00:00
lastmod: 2020-10-06T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "welcome"
weight: 100
toc: true
---

Welcome to the FakeCo API Documentation site - here you'll find the resources necessary to start building with the FakeCo APIs.

### Our APIs

FakeCo has 2 APIs to choose from, the one you develop with will be driven by the use-cases that you are developing for - so choose wisely!

#### Marketplace API

_API Type: GraphQL_

Examples of when you'd use this API are:
- You need access to data marketplace-wide
- You are building your own custom (headless) front end
- You are building into an existing eCom front end
- You want to manage marketplace categorizations (Taxonomy)



{{< alert icon="👉" text="Typically only the <b>Marketplace Operator</b> will use this API." >}}


#### Seller API

_API Type: REST_

Examples of when a Seller would use this API are:
- When you want to auto-create Products
- When you want to retrieve your Invoices
- When you want to set stock levels
- When you want to mark orders as shipped  

#### Webhooks

Webhooks can be used at both a Marketplacer and Seller level. They provide a way to obtain near real-time event notifications on the marketplacer objects of your choosing. Additionally you can define both the event payloads as well as the events you want to be notified on. We currently support webhooks natively on the following objects:

- Adverts* (Products)
- Invoices
- Refund Requests
- Shipments*
- Variants

{{< alert icon="👉" text="Advert and Shipment objects not currently supported at the <b>Seller</b> level" >}}

#### At a Glance

As summary of the objects that each API can work with is shown below, remembering that that the _Seller API_ works only with an individual sellers data...

![Content Type Header](../glance.png)


### Quick Start

Now that your comfortable with both our APIs, (and Webhooks), it's probably time for you to jump in and and get started. The Quick Start Guides listed below should get you up and running with a minimum of fuss:

- Marketplacer API
- Seller API
- Webhooks

### FAQs

Get answers to some of the most commonly asked questions on using our APIs, including but not limited to:

- How to I create a Product (end to end) with the Seller API
- How to I add meta data to my objects
- How do I paginate result sets with GraphQL



