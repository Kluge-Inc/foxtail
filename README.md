Foxtail
=======

Foxtail is a flexible file store-and-retrieve solution, targeted on scalability and decentralization.

System consists of storage nodes called 'spikes'. Every spike serve as an interface to a different kind of storage. Right now three spike types are outlined:
- **storage-spike** - node that stores files in its local filesystem, and provides RESTful interface for file retrieval
- **cliend-spike** - node that stores files on client filesystem (think Dropbox and Google Disk)
- **cdn-spike** - node that provides interface to CDN clouds

All spikes can be subscribed to different file categories. For example, if user uploads file under 'document' category, only those spikes who are storing documents will reply. 

With an addition of **foxtail-gateway** and AMQP messaging we can route upload request to the best-suited storage-spike based on its load, availability and category subscription.

Future plans include sub-category sharding among storage spikes and use of p2p communications between spikes during distribution phase.

![architecture-abstract](./docs/diagrams/foxtail-abstract.png)