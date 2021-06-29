# 🐘 pg-journal
[![license](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/StevePavlin/pg-journal/blob/master/LICENSE)


**pg-journal** is an open source CQRS/Event Sourcing library for Node.js/PostgreSQL inspired by the works of Akka and multiple experimental event store attempts in [Immutable Stack](https://github.com/StevePavlin/immutable-stack).

The goal of the library is to:
 - Provide a reusable set of functionality without lock-in that can be used to selectively apply CQRS/Event Sourcing in real world apps where its needed.
 

# 🏷 Features

- ✅ Gapless global ordering **without exclusive table locks** on the event journal
- ✅ In order batch streaming from all streams for projections
- ✅ Opinionated projection library for Postgres with exactly once processing
- ✅ Opinionated optimistic concurrency retry policy
- ✅ Write/streaming benchmarks on different hardware against popular event stores such as ([EventStoreDB](https://eventstore.com) & [AxonServer](https://axoniq.io/product-overview/axon-server))
- ✅ **Real world** example demo apps
- ✅ 100% test coverage

# ✨ Live Demo

WIP


# 🙏🏻 Road map (MVP)
- 🔯 Persistent subscriptions with the [competing consumers](https://www.enterpriseintegrationpatterns.com/patterns/messaging/CompetingConsumers.html) pattern with Postgres
- 🔯 Opinionated projection library for Redis
- 🔯 Deploy one of the example apps to Heroku or AWS with a simple user interface 
- 🔯 Delayed commands with at least once delivery ([deadlines](https://docs.axoniq.io/reference-guide/v/3.3/part-ii-domain-logic/deadlines)) 


# 🙏🏻 Road map (Future)
- 🔯 Persistent subscriptions with the [competing consumers](https://www.enterpriseintegrationpatterns.com/patterns/messaging/CompetingConsumers.html) pattern with Kafka
- 🔯 Support for table partitioning for [faster btree rebuilds](https://axoniq.io/blog-overview/eventstore)
- 🔯 Archiving to AWS S3 of old partitions
- 🔯 Seamless replication between clusters for blue-green deployments



# 🖥 Installation

```
TODO publish to npm after MVP complete
$ yarn add @pg-journal/event-store
$ yarn add @pg-journal/projection-plugin-postgres
```

# ✍ Basic Usage

- **pg-journal** requires an instance of [pg](https://github.com/brianc/node-postgres) in its constructor.
- `ProjectionStore` is an opinionated projection API for postgres checkpointing if you decide to use postgres for one of your read models.

```js
TODO
```

# 🧪 Contributing

Pull requests are welcome 😃 Tests/linting rules should pass to be merged into mainline.

- Bootstrap dev dependencies in root - `npx lerna bootstrap`
- Bootstrap infrastructure, databases and schemas in a package - `yarn test:setup`
- Run tests - `yarn test`


#### Test suites
- Unit tests are using within each packages functional core to test inputs/outputs
- Integration tests are using within each packages boundary to test its database contract
- System tests are using in the `examples` folder to test integration between multiple package versions so atomic changes can be made


# License

This project is licensed under the terms of the [MIT license](/LICENSE).