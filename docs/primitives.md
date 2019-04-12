# Primitives

Continuous delivery is a broad topic and this page is to serve as a dictionary
to the different primitives that reside inside of Scipian. Keep in mind that
this page is an active document and some of the primitives have not been fully
documented yet, as the RFC process will help in that effort. Also, this page
will eventually be broken up into sub-pages.

## Infrastructure

### Immutable

Does any of this sound familiar:

- One time hacks during outages, We'll put it back into "insert favorite
configuration management tool" later.
- Cron jobs spring up in unexpected places, running obscure, but critical
functions that only one person knows about.
- Application code is deployed outside of the normal
straight-from-source-control process.
- The system becomes finicky. It only accepts deploys in a certain manual way.
- The init scripts no longer work, unless you do something special and
unexpected.
- The operating system has been patched again and again in line with the
standard operating procedures and the inevitable entropy sets in. Or worse, it
has never been patched and now you're too afraid of what would happen if you
try.
- The system inevitably becomes a house of cards. You fear any change and you
fear replacing it since you don't know everything about how it works.

Historically, a server that had an uptime of a year or more was a badge of honor
for an system administrator. However, we have always had the same opinion as
this quote:

> As a system administrator, one of the scariest things I ever encounter is a
server that’s been running for ages. If you absolutely know a system has been
created via automation and never changed since the moment of creation, most of
the problems disappear.

\- Chad Fowler, [Trash Your Servers and Burn Your Code][immutable-fowler],
2013

What if we take the terminology of immutability in software and apply it to
infrastructure, which is the question that Chad proposes? This is the path we
have taken inside of Scipian and it's infrastructure primitives. Distributed
systems are really complicated and we shouldn't be complicating it by also
having lots of mutability.

If you want to learn more about `why immutable`, here are some
references that can help:

1. [Trash Your Servers and Burn Your Code][immutable-fowler], Chad Fowler,
2013
1. [An Introduction to Immutable Infrastructure][immutable-stella], Josh Stella,
2015
1. [Making Immutable Infrastructure Simpler with LinuxKit][immutable-gent],
Justin Cormack, 2018

[immutable-fowler]: http://chadfowler.com/2013/06/23/immutable-deployments.html
[immutable-stella]: https://www.oreilly.com/ideas/an-introduction-to-immutable-infrastructure
[immutable-gent]: https://www.cloudatomiclab.com/immutable-gent/

### Providers

#### Accounts

### Stack

#### Resources

### Network

### Firewall

### Load Balancers

### Kubernetes

### Serverless

### Messaging/Event Driven

## Deployments

### Blue/Green

### Highlander

### Canary

## Observability

### Event Driven

What events are we interested in?
- Logging
- Metrics
- Tracing
- Errors

## Change Management

## Auditing

### What and How We Audit

Each audit event answers:
- What happened?
- When did it happen?
- Who did it?
- Where was it initiated?
- What did it happen on?
- Where was it observed?

Example:

```json
{
    "metadata": {
        "creationTimestamp": "2018-12-13T20:18:13Z"
    },
    "level": "Request",
    "timestamp": "2018-12-13T20:18:13Z",
    "auditID": "277da1b5-16aa-4a1b-ae0f-4d1cdb2cc67a",
    "stage": "ResponseComplete",
    "requestURI": "/api/v1/namespaces/default/runs/plt-network-58f9bd8b6f-ngx8s",
    "verb": "get",
    "user": {
        "username": "system:node:ip-10-0-100-113.us-west-2.compute.internal",
        "groups": [
            "system:nodes",
            "system:authenticated"
        ]
    },
    "sourceIPs": [
        "34.217.76.189"
    ],
    "objectRef": {
        "resource": "runs",
        "namespace": "default",
        "name": "plt-network-58f9bd8b6f-ngx8s",
        "apiVersion": "v1"
    },
    "responseStatus": {
        "metadata": {},
        "code": 200
    },
    "requestReceivedTimestamp": "2018-12-13T20:18:13.388833Z",
    "stageTimestamp": "2018-12-13T20:18:13.389856Z"
}
```

### What happened?

```json
{
    "verb": "get"
}
```

### When did it happen?

```json
{
    "stage": "ResponseComplete",
    "metadata": {
        "creationTimestamp": "2018-12-13T20:18:13Z"
    },
    "requestReceivedTimestamp": "2018-12-13T20:18:13.388833Z",
    "stageTimestamp": "2018-12-13T20:18:13.389856Z"
}
```

### Who did it?

```json
{
    "user": {
        "username": "system:node:ip-10-0-100-113.us-west-2.compute.internal",
        "groups": [
            "system:nodes",
            "system:authenticated"
        ]
    }
}
```

### Where was it initiated?

```json
{
    "sourceIPs": [
        "34.217.76.189"
    ]
}
```

### What did it happen on?

```json
{
    "objectRef": {
        "resource": "runs",
        "namespace": "default",
        "name": "plt-network-58f9bd8b6f-ngx8s",
        "apiVersion": "v1"
    }
}
```

### Where was it observed?

Literally always Scipian

### Audit Stages

![Audit Event Stages][audit-event-stages]

[audit-event-stages]: assets/audit-event-stages.png

### Auditing Levels

*Level is determined by policy*

- **None**: no requests are logged
- **Metadata**: only request metadata is logged
- **Request**: request object is logged 
- **RequestResponse**: request & response objects are logged

### Audit Policy Example

```yaml
apiVersion: audit.k8s.io/v1
kind: Policy
omitStages:
- "RequestReceived"
rules:
- level: Metadata
  resources:
  - group: ""
    resources: [
      "secrets"
    ]
```

### Output

```json
{
    "level": "Metadata",
    "timestamp": "2018-12-13T17:02:25Z",
    "stage": "ResponseComplete",
    "requestURI": "/api/v1/namespaces/default/secrets/api-key",
    "verb": "get",
    "user": {
        "usename": "daler"
    },
    "sourceIPs": [
        "10.0.143.187"
    ],
    "objectRef": {
        "resource": "secrets",
        "namespace": "default"
    },
    "requestReceivedTimestamp": "2018-12-13T17:02:25.399627Z",
    "stageTimestamp": "2018-12-13T17:02:25.400717Z"
}
```

### Audit Summary

- **Levels:** how deep to log
- **Stages:** when to log

## Black Out Dates

## Feature Gates

## Chaos

## Tenant
