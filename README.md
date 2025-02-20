# Streaming Data Processing using PySpark

### Overview
This repository contains an experiment that simulates vote counting in the 2024 U.S. Elections using PySpark for real-time data processing.

#### Step 1 - Simulating the Vote Data
The first step of this project involves simulating votes recorded in the 2024 U.S. Elections. To achieve this, the script developed using the Faker library generates up to 50 JSON files, each containing detailed vote information for one of the 50 U.S. states. Each JSON file records individual vote details, including:
- A unique vote ID
- Timestamp
- State
- Voter age group
- Selected candidate

The JSON files are created every 5 seconds, simulating the continuous arrival of new votes in real-time. These files are stored in the `vote_stream` folder.
To optimize computational resources, the script uses a dictionary containing all 50 U.S. states and samples 0.5% of the eligible voting population in each state. Each JSON file contains approximately 20,971 votes. Additionally, the script runs in a separate thread to ensure that data generation does not interfere with the streaming processing.

> [!WARNING]
> The data is randomly generated, and the final results do not represent any real projections or predictions of the election outcomes.

#### Step 2 - Spark Configuration and Streaming Initialization
In this step, the Spark environment is set up to process streaming data. The code defines the schema for the input data and initializes the data stream from the `vote_stream` local folder.

#### Step 3 - Streaming Data Processing
In the final step, votes are processed in streaming mode to calculate the real-time vote count for each candidate. The script performs the following operations:
- Groups votes by candidate.
- Computes and displays the vote count for each candidate.

<br>

### Requirements
To run this experiment, install the following dependencies:

```bash
pip install pyspark faker
```

### Usage
To start the simulation and streaming processing, execute the script:

```bash
python vote_streaming.py
```

### License
This project is licensed under the GNU3 License - see the [LICENSE](LICENSE) file for details.

<br><br>

> [!NOTE]  
> Created for the Massive Data Processing course, taught by Prof. Alexandre Vaz at IESB.
