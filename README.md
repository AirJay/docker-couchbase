## Couchbase Dockerfile

This repository contains a **Dockerfile** that can be used to create a cluster of Couchbase nodes


### Installation

1. Install [Docker](https://www.docker.io/).

2. Download [trusted build](https://registry.hub.docker.com/u/airjay/couchbase/) from public [Docker Registry](https://index.docker.io/): `docker pull airjay/couchbase`

### Usage

1. Create first node (with optional sample bucket) `docker run -d --name couch_one -p 11210:11210 -p 8091:8091 -p 8092:8092 -e CLUSTER_INIT_USER=Administrator -e CLUSTER_INIT_PASSWORD=password -e SAMPLE_BUCKETS=\"sample\" airjay/couchbase`

2. Create second node linked to the first `docker run -d --name couch_two --link couch_one:couchbase -e CLUSTER_INIT_USER=Administrator -e CLUSTER_INIT_PASSWORD=password airjay/couchbase`
