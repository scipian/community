# Introduction to Scipian

## What is Scipian?

Scipian is an open source platform to give teams a single, self-service place to
access all the tools and services needed to develop and deploy applications. To
put it more simply, it's a continuous delivery platform that combines disparate
tools and utilities to create affinity around developing and deploying
applications. It is not tools/platforms like GitHub Enterprise, Artifactory,
Kubernetes, or OpenStack.

The value stream behind Scipian is to focus on speed and agility - bringing new
innovation and technology to support business strategy. Scipian is propelling
the engineers to build applications by enabling them to focus on what they do
best - write code, operations, or administration.

Definition:
> The word `Scipian` originates from Old English, meaning to send or transport
(merchandise, people) by ship and is the root of [ship][ship-root].

[ship-root]: http://www.etymonline.com/index.php?allowed_in_frame=0&search=scipian

## Why Scipian?

### History

As with anything, when working with legacy systems and platforms inside an
enterprise business, we needed to understand the past before we can solve for
the future.

#### In the beginning... I think I need a server?

  1. Engineer team needs to build a new application
  1. Reach out to infrastructure team
  1. Infrastructure team places an order for servers
  1. Wait some time ...
  1. Servers arrive
  1. Infrastructure team racks the servers
  1. Infrastructure turns the servers over to the engineering team

Sounds simple, but at the same time very complex. We've abstracted some of this
with virtualization and handed API's over to the teams to help mitigate the
steps above. However, it was only incremental benefits and it introduced other
problems.

#### Infrastructure Change Fatigue

Engineering teams who got their pet servers spent a lot of time patching, even
with new things like OpenStack and etc., we still asked teams to do a lot of
work to make changes to support the platform, upgrades, migrations, and etc.
This infrastructure work culminated into the teams backlogs and it's been
destructive for them.

The engineering teams were not alone, as the infrastructure teams spent a lot of
time tracking abandoned and new servers, doing server upgrades, and etc.

The true loss here was the customer, as teams weren't agile enough to get
something to market fast enough.

#### Disparate Experiences

From an product engineering standpoint, teams have a very disparate experience.
They need to deploy applications to internal data centers and a cloud provider
like Amazon Web Services, Google Cloud Platform, and Microsoft Azure. Deployment
is very different between the options, which caused the engineering teams to
create deployment tools, which meant they had to build them and maintain the
toolchains. This can reach up to NaN% of their time to get a deployment out for
the first time. Then on top of this, there are no standards on how a team can
implement logging, monitoring, and tracing which are basic operational tasks.
Without those standards, it's hard for engineering teams to understand the best
patterns around observability.

TODO(dwr): Replace NaN% with a real value after researching

#### Compliance

To compound on the above, everything is wrapped with compliance in mind, which
in the past meant putting a ticket system in place to have another party do the
task, such as deploying an new release. This stifles agility as engineers are
focused on making new features, managers are focused on developing business
value, and operations is focused on keeping everything alive. Since the process
of collaboration and cooperation between these roles is left to chance, it’s
often full of friction.

We can do better.

#### How

If the above resonates with you and your teams, we hope you'll continue to read
to learn how we plan to solve the above with Scipian. However, before we can
discuss the how, we first need to discuss and define the who.

> The __Front Line Engineer__ is someone who is working to deliver value for
your customers.

The front line engineer is somebody who can start with nothing or existing
resources. They may of interacted with the platform before or it could be their
first day. Their day could range from fixing a bug, implementing a feature, or
building a proof of concept for their idea. If they cannot fully demo that bug
fix, feature, or proof of concept the next day without having a meeting or 
filing a ticket in what ever ticketing system you use, then we have failed.

Now that we have a _who_, we can concentrate on the how and come up with some
principles for the platform to live by.

1. __Self Service__ - Zero meetings with the platform team, up and running to
empower the engineering teams to get their project off the ground.
1. __Cohesive Usability__ - Create affinity around using the platform in a
chohesive way and getting rid of disparate experiences.
1. __Discoverability__ - A team should be able to ascertain the abilities of the
platform with intuitiveness. No searching wiki pages or trying to find tribal
knowledge.
1. __Availability__ - The platform needs to be up all the time, 24x7x365. There
will not be maintenance windows and dev is production.
1. __Trust With Accountability__ - Everything in the platform will be auditable
and policy driven using RBAC principles.
1. __Inception__ - Scipian uses scipian by bootstrapping scipian with itself.
1. __Opinions, Loosely Held__ - The decisions we make today around the
internal components of the platform, may not be the right decisions for the
internal components tomorrow.

To that end, we use the above principles to create the __happy path__ for that
front line engineer.

There needs to be a clear separation between infrastructure and engineers by
making delivery predictable and functional. For example, infrastructure as code
is not checking YAML's into a git repository. Instead, it should be declarative,
where given inputs for Foo Application, the infrastructure will do X.

Successful decoupling of infrastructure, services, and teams minimizes the need 
for manual coordination, reduces cost and complexity, and significantly 
increases engineer velocity, operational efficiency, and business 
productivity. It delivers a framework, implementation, and operating model to 
ensure consistency across an open, hybrid, and multi-cloud future.

There will be four measures, that we are taking from the
book [Accelerate][accelerate], to determine the success of the project.

1. **Lead Time:** time from a customer making a request to the request being satisfied.
1. **Deployment Frequency:** how often do things get into production, per developer.
1. **Mean Time to Restore (MTTR):** how long it takes to recover from a system outage or failure.
1. **Change Fail Percentage:** how often a change introduces a bug, fails to fix the problem, causes an outage, or fails to deploy.

[accelerate]: https://www.amazon.com/Accelerate-Software-Performing-Technology-Organizations/dp/1942788339
