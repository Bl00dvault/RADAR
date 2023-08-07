# RADAR - Requirement And Data Analysis Reporter

## Goals
- Generate data collection requirements based on MITRE techniques and defined environment variables that satisfies high-level data quality characteristics
- Develops a (heat) map of data collection coverage based on high-level data quality characteristics that satisfies a given scenario, overlaid on a notional map
- Uses MITRE ATT&CK Flow to visualize the hypothesized scheme of maneuver
- Outputs a list of commands to collect the data based on selected capabilities grouped by Technique satisfied 
- Outputs a list of commands to collect the data based on high-level data quality characteristics
- Similar to [DeTTECT](https://github.com/rabobank-cdc/DeTTECT), but focused more on specifics and Compromise Assessments


### Data Quality
#### Accuracy
- Characteristics Description: A quality of that which is free of error. A qualitative assessment of freedom from error, with a high assessment corresponding to a small error (FIPS Pub 11-3)
- Example Metric: Percent of values that are correct when compared to the actual value. For example, M=Male when the subject is male.

#### Completeness
- Characteristics Description: Completeness is the degree to which values are present in the attributes that require them (Data Quality Foundation)
- Example Metric: Percent of data fields having values entered into them. Data sources missing data, not being parsed/split properly. Endpoint data is only available from high value targets and for a week only.
- Description: Also referred as "Availability" is the degree to which data is not missing, is of sufficient breadth and depth, and available for the intended purpose
- Questions: Are all the required/needed data fields and values recorded? How much data that is required/needed is available and for how long?


#### Consistency
- Characteristics Description: Consistency is a measure of the degree to which a set of data satisfies a set of constraints (Data Quality Management and Technology)
- Example Metric: Percent of matching values across tables/files/records

#### Timeliness
- Characteristics Description: As a synonym for currency, timeliness is a measure of the degree to which data is current with the real-world object or event being described (Data Quality Management and Technology)
- Example Metric: Percent of data available within a specified threshold time frame (e.g., days, hours, minutes)

#### Uniqueness
- Characteristics Description: The state of being the only one of its kind. Being without an equal or equivalent
- Example Metric: Percent of records having a unique primary key

#### Validity
- Characteristics Description: The quality of data that is founded on an adequate system of classification and is rigorous enough to compel acceptance (DoD 8320.1-M)
- Example Metric: Percent of data having values that fall within their respective domain of allowable values

## MindMap
Create a mindmap for how all the terms relate, and the specific references

## Usage
The user must supply:
- Environment (Targets)
  - OS, OS version, OS architecture, etc.
  - Hosts
- Hypothesized Scheme of Maneuver (Technique Coverage)
  - MITRE Tactics/Techniques
- Capabilities (Collectors)
  - Security Onion
  - Commercial EDR (Carbon Black, Endgame, etc.)
  - Sysmon or other native data enrichment capabilities

The tool provides:
- Data collection requirements and the coverage based on MITRE techniques (and their associated data source) and defined environment variables
- Visualization of the environment with data collected (heat map) and MITRE ATT&CK Flow

## Workflow
1. Analyze capabilities that are available in the environment
2. Map the capabilities to the associated data source they will collect and their MITRE technique



## Sources
- Defining data collection requirements
https://posts.specterops.io/defenders-think-in-graphs-too-part-2-b1fd751525d1

https://posts.specterops.io/thoughts-on-host-based-detection-techniques-21d9c97082ce

https://cyberwardog.blogspot.com/2017/12/ready-to-hunt-first-show-me-your-data.html

