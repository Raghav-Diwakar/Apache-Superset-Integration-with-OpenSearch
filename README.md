# Test Case: Apache Superset Integration with OpenSearch

**Submitted By**: Raghav\
**Submitted To**: Mrs Nitu Gupta.


## Goal

The goal of this project is to explore Apache Superset, connect it to an OpenSearch database, and create impressive dashboards using publicly available datasets.

## Table of Contents

- [Test Case: Apache Superset Integration with OpenSearch](#test-case-apache-superset-integration-with-opensearch)
  - [Goal](#goal)
  - [Table of Contents](#table-of-contents)
    - [Test Environment](#test-environment)
    - [TC1: Install Apache Superset using Docker](#tc1-install-apache-superset-using-docker)
    - [TC2: Install OpenSearch using Docker](#tc2-install-opensearch-using-docker)
    - [TC3: Configure OpenSearch Connection in Superset](#tc3-configure-opensearch-connection-in-superset)
    - [TC4: Load Dataset into OpenSearch](#tc4-load-dataset-into-opensearch)
    - [TC5: Create a Dataset in Superset](#tc5-create-a-dataset-in-superset)
    - [TC6: Build and Configure Charts](#tc6-build-and-configure-charts)
    - [TC7: Assemble a Dashboard](#tc7-assemble-a-dashboard)
    - [TC8: Apply Customizations and Filters](#tc8-apply-customizations-and-filters)
    - [TC9: Validate Dashboard Performance](#tc9-validate-dashboard-performance)
    - [TC10: Verify Data Updates in Superset](#tc10-verify-data-updates-in-superset)

---

### Test Environment

- Apache Superset running in Docker
- OpenSearch running in Docker with SQL plugin enabled
- Sample dataset available in OpenSearch index

---

### TC1: Install Apache Superset using Docker

**Scenario**: Deploy Apache Superset using Docker.\
**Given**: A system with Docker installed.\
**When**: Running the `docker-compose` setup.\
**Then**: Superset should be accessible at `http://localhost:8088`.

Commands:

```sh
git clone https://github.com/apache/superset.git
cd superset
docker-compose -f docker-compose-non-dev.yml up
```

**Test Run Date**: 08/03/2025\
**Result**: Pass\
**Testing Outputs**: 

---

### TC2: Install OpenSearch using Docker

**Scenario**: Deploy OpenSearch using Docker.\
**Given**: A system with Docker installed.\
**When**: Running OpenSearch containers.\
**Then**: OpenSearch should be accessible and operational.

Commands:

```sh
docker network create opensearch-net
docker run -d --name opensearch-node1 --net opensearch-net -p 9200:9200 -p 9600:9600 -e "discovery.type=single-node" -e "OPENSEARCH_INITIAL_ADMIN_PASSWORD=admin" opensearchproject/opensearch:latest
```

**Test Run Date**:08/03/2025\
**Result**: Pass\
**Testing Outputs**: 

---

### TC3: Configure OpenSearch Connection in Superset

**Scenario**: Add OpenSearch as a database source in Superset.\
**Given**: Superset is running.\
**When**: Configuring the connection string.\
**Then**: Superset should connect to OpenSearch successfully.

Connection string:

```
opensearch+https://admin:admin@localhost:9200
```

**Test Run Date**:08/03/2025\
**Result**: Pass\
**Testing Outputs**: 

---

### TC4: Load Dataset into OpenSearch

**Scenario**: Upload a publicly available dataset to OpenSearch.\
**Given**: OpenSearch is running.\
**When**: Importing data.\
**Then**: The data should be available in OpenSearch.

**Test Run Date**: 08/03/2025\
**Result**: Pass\
**Testing Outputs**: 
---

### TC5: Create a Dataset in Superset

**Scenario**: Define a dataset in Superset using the OpenSearch connection.\
**Given**: OpenSearch is connected to Superset.\
**When**: Creating a new dataset from the OpenSearch index.\
**Then**: The dataset should be available for visualization.

**Testing Outputs**: 

---

### TC6: Build and Configure Charts

**Scenario**: Create charts using the dataset in Superset.\
**Given**: A dataset is available in Superset.\
**When**: Configuring and generating charts.\
**Then**: The charts should correctly visualize the dataset.

**Testing Outputs**: 

---

### TC7: Assemble a Dashboard

**Scenario**: Combine multiple charts into a dashboard.\
**Given**: Charts are created in Superset.\
**When**: Assembling them into a dashboard.\
**Then**: The dashboard should be visually appealing and functional.

**Testing Outputs**: 

---

### TC8: Apply Customizations and Filters

**Scenario**: Enhance the dashboard with custom filters and design changes.\
**Given**: A dashboard is created.\
**When**: Adding filters, themes, and interactivity.\
**Then**: The dashboard should allow dynamic interactions.

**Testing Outputs**: 

---

### TC9: Validate Dashboard Performance

**Scenario**: Ensure the dashboard loads efficiently with large datasets.\
**Given**: A complex dataset is used.\
**When**: Testing performance and responsiveness.\
**Then**: The dashboard should perform well without lag.

**Testing Outputs**: 

---

### TC10: Verify Data Updates in Superset

**Scenario**: Ensure real-time data updates in the dashboard.\
**Given**: The OpenSearch data changes.\
**When**: Refreshing the dashboard.\
**Then**: The updates should reflect in Superset.

**Testing Outputs**: 

---

