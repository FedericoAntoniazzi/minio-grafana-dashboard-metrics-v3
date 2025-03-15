# MinIO Metrics v3 Grafana Dashboard

## Overview

This repository contains a community-maintained Grafana dashboard for MinIO object storage using the new Metrics v3 API.
This project was created in response to MinIO's deprecation of Metrics v2 and their decision to focus solely on their embedded dashboard solution
rather than supporting external Grafana dashboards (see [minio/minio#20678](https://github.com/minio/minio/issues/20678)).

This dashboard is based on the popular [MinIO Dashboard (#13502)](https://grafana.com/grafana/dashboards/13502-minio-dashboard/) from Grafana's marketplace,
updated to work with MinIO's Metrics v3 API.

## Why This Project Exists

MinIO has deprecated their Metrics v2 API and shifted focus to their embedded dashboard solution.
While this works for many users, there are several reasons you might prefer a Grafana dashboard:

- Integration with existing monitoring infrastructure
- Customization capabilities beyond what the embedded dashboard offers
- Unified monitoring across different systems in your infrastructure
- Advanced alerting and notification features available in Grafana

## Features

- **Updated for Metrics v3**: Fully compatible with MinIO's new metrics format
- **Based on Established Dashboard**: Builds upon the widely-used MinIO Dashboard (#13502)
- **Drop-in Replacement**: Designed to replace dashboards that were using the deprecated Metrics v2
- **Comprehensive Metrics**: Monitors key MinIO performance indicators including:
  - Throughput (read/write operations)
  - Request latency
  - Error rates
  - Disk usage and capacity
  - Node health status
  - S3 API usage statistics

## Installation

### Prerequisites

- Grafana (version 9.x or newer recommended)
- MinIO configured with Prometheus metrics enabled
- Prometheus server scraping MinIO metrics endpoints

### Setup Instructions

1. Download or copy the content of `dashboard.json`

2. Import the dashboard into Grafana:
   - Navigate to Grafana → Dashboards → Import
   - Upload the JSON file or copy/paste its contents
   - Select your Prometheus data source
   - Click Import

3. Configure the dashboard variables (if needed) to match your environment

## Configuration

This repository is only responsible for the dashboard.
The configuration guide is available in the [documentation](https://min.io/docs/minio/container/operations/monitoring/metrics-and-alerts.html).

## Migrating from Metrics v2

If you're updating from a dashboard that used MinIO's Metrics v2, note these key differences:

- Metric names have changed (this dashboard accounts for these changes)
- Some metrics have been consolidated or restructured
- New metrics are available in v3 that weren't in v2

## Key Differences from Original Dashboard

This dashboard differs from the original [MinIO Dashboard (#13502)](https://grafana.com/grafana/dashboards/13502-minio-dashboard/) in the following ways:

- Updated all metric queries to use the new Metrics v3 API naming conventions
- Adjusted panel layouts and visualizations to accommodate changes in metric structure

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Limitations

- This is a community-maintained project and is not officially supported by MinIO
- Some advanced features in MinIO's embedded dashboard may not be replicated here
- Dashboard may require updates when MinIO makes changes to their metrics format

## License

This project is licensed under the Apache 2.0 License - see the LICENSE file for details.

## Acknowledgements

- MinIO team for creating an excellent object storage server
- Contributors to the original [MinIO Dashboard (#13502)](https://grafana.com/grafana/dashboards/13502-minio-dashboard/) that served as the foundation for this work
- Community members who have tested and provided feedback

## Disclaimer

This project is not affiliated with or endorsed by MinIO, Inc. MinIO is a trademark of MinIO, Inc.
