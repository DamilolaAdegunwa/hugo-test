---
title: "Webhooks Overview"
description: "Overview of how we use webhooks"
date: 2020-10-13T15:21:01+02:00
lastmod: 2020-10-13T15:21:01+02:00
draft: false
images: []
menu:
  docs:
    parent: "webhooks"
weight: 100
toc: true
---

In this section we cover:

- What are webhooks
- When to use webhooks
- Overview of how webhooks are implemented at Marketplacer

## What are webhooks?

Webhooks is a generic term used to describe an integration pattern where an _information consumer_ registers its interest in receiving "real-time" notifications from an _information provider_. It places the onus of providing updated information with the information provider, with the information consumer acting in a more passive role as a listener, (at least initially - see _When to use webhooks_ for further discussion).

It avoids the potentially less efficient pattern of _polling_, where an information consumer repeatedly requests, (most usually redundant), information updates from the information provider.

Both polling and event driven, (webhook), approaches are illustrated below.

### Polling Example

![Polling Example](../polling.png)

### Webhook Example

![Webhook Example](../webhooks.png)

## When to use webhooks

From an information consumption perspective, webhooks are a good integration approach when:

- You want to avoid polling / batch updates
- You need real-time / just-in-time updates on changes to data

However using webhooks does come with some additional considerations, most especially as an information consumer you'll need to be prepared to process webhook events in an on-demand, ad-hoc basis, which is potentially more complex than processing less infrequent batch queries.

Ultimately the approach you take will be driven by the underlying use cases you're solving for. For example if you want to notify your customers that an order has shipped in real-time, then webhooks would be a good choice. If on the other hand you just need to understand the total number of orders shipped at the close of business, a batch query approach may solve that need more effectively.

## How we use webhooks at Marketplacer

Webhook notifications are triggered against changes to the following Marketplacer entities:

- Adverts (Products)
- Invoices
- Refund Requests
- Shipments
- Variants (Product Variants)

When registering a webhook against any of these entities, users can specify, (via a GraphQL query), what payload they would like returned in relation to that entity, as well as any related entities.

So for example, you can register a webhook against all `Invoices`, but can also choose to retrieve the associated data for:

- The parent Order
- Invoice Amendments
- Refund Requests
- Shipments
- Invoice Line Items

Refer to [GraphQL Voyager](/graphql-voyager) to gain an understaing of our entity relationships.

As webhooks are generated at the entity level for all changes to that entity we attempt to deduplicate redundant notifications where it makes sense to do so (to avoid overly chatty event streams).

### The (sort of) technical bit

Our webhooks work as follows:

- We Generate a HTTP POST Request to a HTTP(S) endpoint of your choosing
- HTTP Body supplied as JSON, which is the result of executing a GraphQL query specified when registering the webhook
- Additional HTTP headers can be configured as required


For a step by step guide on how to set up and work with webhooks in Marketplacer, please go to the [Getting Started Guide](/webhooks/getting_started)