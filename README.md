<p align="center">
  <img width="460" height="100%" src="./assets/luxor-relay.png">
</p>

Luxor Relay
===========
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]

`luxor-relay` is a stratum-compatible proxy that assists with managing large
scale ASIC deployments.

- Single connection for up to 65000 miners.  This reduces the load on datacenter networking gear.
- Manages connection redundancy. If the pool disconnects, miners don't drop.
- Lower bandwidth - Relay compresses the miner shares by up to 90%.
- Improved efficiency and reduces stales.
- Incredible view of stratum statistics.  Every share gets accounted for in our
    custom built dashboards.
- Simple setup. Just install docker and run `docker compose up`.
- Multi-tenancy - supports multiple usernames with a single Relay deployment.
- Low memory footprint - works on most devices.


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/LuxorLabs/docker-stratum-relay.svg?style=for-the-badge
[contributors-url]: https://github.com/LuxorLabs/docker-stratum-relay/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/LuxorLabs/docker-stratum-relay.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/LuxorLabs/docker-stratum-relay.svg?style=for-the-badge
[stars-url]: https://github.com/LuxorLabs/docker-stratum-relay/stargazers
[issues-shield]: https://img.shields.io/github/issues/LuxorLabs/docker-stratum-relay.svg?style=for-the-badge
[issues-url]: https://github.com/LuxorLabs/docker-stratum-relay/issues

Getting Started
---------------
To get started with Luxor Relay, there are a few requirements for your computer.
We highly recommend setting up a machine on-premise in the datacenter.

First, we must install Docker. You can do that [here](https://www.docker.com/get-started).

The latest versions of Docker on certain operating systems includes docker-compose by default. However, some OS have `docker-compose` as a seperate package. You can view your operating system settings through the setup guide [here](https://docs.docker.com/compose/install/).

Once Docker is installed, clone this repo into your local system:
```
git clone https://github.com/LuxorLabs/docker-stratum-relay.git
```

Then `cd` into the root directory:
```
cd docker-stratum-relay
```

Finally, you can bootup the entire Luxor Relay stack with docker-compose.

If you have a Docker instance with compose built in you can run:
```
docker compose up
```

If you have a Docker instance with a seperate `docker-compose` installation, you
can run:
```
docker-compose up
```

Notice the main difference is the `-` which references the specific binary we're
using.

To stop Luxor Relay at any time, just run `docker compose down` or
`docker-compose down`, depending on your system setup.

You can also run the Docker containers in the background with:
```
docker compose up -d
```

System Requirements
---------------
The full Relay installation will require:
- 500Mb of disk space for the docker images
- 250Mb of memory for the Grafana + Prometheus metrics

Accessing the Dashboard
-----------------------
Luxor Relay comes with a full metrics suite for analyzing share data and
hashrate efficiency. We use Grafana and VictoriaMetrics to achieve this. You can
access the dashboard once the `docker-compose` stack is up by going to
`http://localhost:3010/d/relay/luxor-relay-metrics` in your browser.

Happy hashing!








