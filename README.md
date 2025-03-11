# Test Case: Apache Superset Integration with OpenSearch

**Submitted By**: Raghav\
**Submitted To**: Ms Nitu Gupta.


## Goal

The goal of this project is to explore Apache Superset, connect it to an OpenSearch database, and create impressive dashboards using publicly available datasets.

## Table of Contents

### Apache Superset & OpenSearch Integration Test  

#### 1. Goal  
#### 2. Table of Contents  
   - **Test Environment**  
   - **TC1:** Install Apache Superset (Docker)  
   - **TC2:** Install OpenSearch (Docker)  
   - **TC3:** Configure OpenSearch in Superset  
   - **TC4:** Load Dataset into OpenSearch  
   - **TC5:** Create a Dataset in Superset  
   - **TC6:** Build & Configure Charts  
   - **TC7:** Assemble a Dashboard  
   - **TC8:** Apply Customizations & Filters  
   - **TC9:** Validate Dashboard Performance  

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
**Expected Output**: Apache Superset Installed and contains all file.

**Testing Outputs**: 
![Output1 File](File1.png)

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
**Expected Output**: Opensearch Installed and active.

**Testing Outputs**: 

![Output File](File2.png)
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
**Expected Output**: Opensearch Connected with Superset.

**Testing Outputs**: 

![Output File](File3.png)
---

### TC4: Load Dataset into OpenSearch

**Scenario**: Upload a publicly available dataset to OpenSearch.\
**Given**: OpenSearch is running.\
**When**: Importing data.\
**Then**: The data should be available in OpenSearch.


**Test Run Date**:09/03/2025\
**Result**: Pass\
**Expected Output**: Dataset Available and access with Superset.

**Testing Outputs**: 

![Output File](File4.png)
---

### TC5: Create a Dataset in Superset

**Scenario**: Define a dataset in Superset using the OpenSearch connection.\
**Given**: OpenSearch is connected to Superset.\
**When**: Creating a new dataset from the OpenSearch index.\
**Then**: The dataset should be available for visualization.

**Test Run Date**:09/03/2025\
**Result**: Pass\
**Expected Output**: All attribute of dataset in defined order and sorted for dashboard.

**Testing Outputs**: 

![Output File](File5.png)
---

### TC6: Build and Configure Charts

**Scenario**: Create charts using the dataset in Superset.\
**Given**: A dataset is available in Superset.\
**When**: Configuring and generating charts.\
**Then**: The charts should correctly visualize the dataset.

**Test Run Date**:09/03/2025\
**Result**: Pass\
**Expected Output**: Build Chart of dashboard presented and customize.

**Testing Outputs**: 

![Output File](File6.png)
---

### TC7: Assemble a Dashboard

**Scenario**: Combine multiple charts into a dashboard.\
**Given**: Charts are created in Superset.\
**When**: Assembling them into a dashboard.\
**Then**: The dashboard should be visually appealing and functional.

**Test Run Date**:10/03/2025\
**Result**: Pass\
**Expected Output**: Assemble all chart in dashboard presented for hosted.

**Testing Outputs**: 

![Output File](File7.png)
---

### TC8: Apply Customizations and Filters

**Scenario**: Enhance the dashboard with custom filters and design changes.\
**Given**: A dashboard is created.\
**When**: Adding filters, themes, and interactivity.\
**Then**: The dashboard should allow dynamic interactions.

**Test Run Date**:10/03/2025\
**Result**: Pass\
**Expected Output**: Apply for Universal Customzation on all Charts.

**Testing Outputs**: 

![Output File](File8.png)
---

### TC9: Validate Dashboard Performance

**Scenario**: Ensure the dashboard loads efficiently with large datasets.\
**Given**: A complex dataset is used.\
**When**: Testing performance and responsiveness.\
**Then**: The dashboard should perform well without lag.

**Test Run Date**:10/03/2025\
**Result**: Pass\
**Expected Output**: Apply Filter on dashboard and check all working as expected.

**Testing Outputs**: 

![Output File](File9.png)

---

