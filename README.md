# Prometheus & Grafana Integration

## Overview

This repository provides a comprehensive guide and resources to set up Prometheus integrated with Grafana. These tools are essential for monitoring and visualizing metrics from your systems and applications, allowing you to gain insights into performance and availability.

## Features

- **Prometheus**: A powerful monitoring and alerting toolkit designed for reliability and scalability.
- **Grafana**: A versatile dashboard and visualization tool that integrates seamlessly with Prometheus to provide real-time data visualization.
- **Docker-Compose**: Simplified setup and management of both Prometheus and Grafana using Docker Compose. (The best for easy deploy :-)

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- **Docker**: [Install Docker](https://docs.docker.com/get-docker/)
- **Docker-Compose**: [Install Docker-Compose](https://docs.docker.com/compose/install/)

## Installation

Follow these steps to set up Prometheus and Grafana:

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/Alek3498/Prometheus.git
    cd Prometheus
    ```
    
2. **Configure Prometheus**:
    - Update the `prometheus.yml` file in the `prometheus-conf` directory to include your specific scrape targets and alerting rules.

3. **Start the Services**:
    - Use Docker Compose to start both Prometheus and Grafana:
    ```bash
    docker-compose up -d
    ```

4. **Access Grafana**:
    - Open your web browser and go to `http://localhost:3000`.
    - Default credentials:
      - Username: `admin`
      - Password: `admin`

    Note: Then you can change the default password

5. **Add Prometheus as a Data Source in Grafana**:
    - Go to **Settings > Data Sources > Add Data Source**.
    - Select **Prometheus** and configure it with the URL `http://prometheus:9090`.

6. **Import Dashboards**:
    - Import pre-configured dashboards or create your own to visualize the metrics collected by Prometheus.

    - In my deployment I used:
        - Dashboard Cadvisor (ID: 14282) for container metric visualization
        - Dashboard Node Exporter Full (ID: 1860) for linux and windows metrics.



## Directory Structure

```bash
prometheus/
│
├── Docker-Lab.png             # Docker server with all containers of this lab
├── Grafana-dashboards.png     # Grafana imported dashboards
├── Prometheus+Grafana-Cadvisor_exporter.png          # Grafana Cadvisor dashboard
├── Prometheus-GUI.png         # Prometheus targets to scrap
├── Promethues+Grafana-Full_node_export.png # Grafana dashboard for Linux/windows node exporters
├── docker-compose.yml         # This file build the whole lab
├── grafana-data_sources.png   # Grafana config where we mapped Prometheus
└── prometheus.yml             # Premethues configuration file.
```

## Usage

- **Monitoring**: Use the Grafana dashboards to monitor your systems in real-time.
- **Alerting**: Configure alerting rules in Prometheus to receive notifications when certain conditions are met.

## Contributing

Contributions are welcome! Please fork this repository and submit a pull request with your changes.



---

This structure should give you a solid starting point for your `README.md`. Feel free to adjust the content based on the specific details of your project.