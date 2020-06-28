Speedrun.com API Middleware
====

This repository provides a tool to (conceptually) clone the `games`, `categories`, `levels`, `variables`, `players`, `runs`, and `leaderboards` endpoints. It maintains a running tail in order to keep database up to date. Additionally, it downloads Twitch streams from active speedrunners.

Goals for this project:
* Fast initial sync time and API performance
* Modular components
* High availability support
* (long term) Support multiple storage backends

Potential uses for this project may be:

* Custom clients or tools which use Speedrun.com API, which require additional processing or management from a intermediate endpoint
* Bulk analysis of Speedrun.com data without 

This tool was originally designed for my [Speedrun Browser for Android](https://github.com/dl00/speedrun-browser-android) app.

## Usage

### TL;DR

With [Docker Compose](https://docs.docker.com/compose/): `docker-compose up`

### Requirements

In order to record data from Speedrun.com, some extra tools are required:

* [Redis](https://redis.io/download) v5+ for state tracking and low-level indexing
* A backing database. Currently supported:
    * [MongoDB](https://www.mongodb.com/try/download/community)

Additionally, minimum system requirements:

* 4GB RAM
* 5GB free disk space for Speedrun.com data
* Dual core CPU

It takes about 4 hours for the initial sync from Speedrun.com API (as of Jun 2020). This speed is mostly constant due to request limits on the Speedrun.com API.

### Getting Started

There are a few easy ways to to start the tool.

#### docker-compose.yml

If you have [Docker Compose](https://docs.docker.com/compose/), you can bring up everything with one command:

```
docker-compose up
```

Access the generated API at `http://localhost:3500`


#### Helm

A helm chart which includes a MongoDB and Redis is provided in the repository.

Instructions on how to use TBC.