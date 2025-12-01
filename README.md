***Smart Traffic Management – Data Analysis***
This project explores a simple Smart Traffic Management (STM) scenario using a structured CSV dataset (STM.csv) and a Jupyter notebook (Smart_traffic_management.ipynb). The goal is to understand traffic conditions at road crossings and support decisions such as signal timing and incident detection.​

**Dataset description**
The dataset contains time-stamped traffic measurements for multiple road crossings and lanes. Each row in STM.csv represents the state of a single lane at a particular time and contains:​

**Crossing_Id**: Identifier of the junction or crossing (for example C1, C2, C3, C4).​

**Lane_Id**: Identifier of the lane or road segment within a crossing (for example R1–R8).​

**Average_Speed**: Average vehicle speed on that lane at the given time.​

**Average_Acceleration**: Average acceleration on that lane at the given time.​

**Time**: Timestamp for the observation (for example 09:18:54).​

**Current_Light_Status**: Encoded traffic light state for that lane (for example L1, L3).​

**Current_Timer**: Remaining time in seconds for the current signal state.​

**Automatic Incident Detection (AID)**: Binary flag where 1 indicates that an incident (such as congestion or abnormal behavior) has been detected on that lane, and 0 indicates normal conditions.​

***Project objectives***
Using this data, the notebook is designed to:​

Load and inspect STM data for multiple crossings and lanes.

Explore how speed, acceleration, signal status, and timer relate to the AID flag.

Provide a basis for simple rules or models that could support traffic signal control or early incident detection in a smart city setting.

**Data loading**

Reads STM.csv into a dataframe structure for easy manipulation.​

Data inspection and cleaning

Displays the first few rows and column names to verify that the data has been loaded correctly.​

Checks basic properties such as the number of rows and columns to confirm dataset shape.​

**Exploratory analysis**

Examines distributions of Average_Speed and Average_Acceleration across lanes and crossings.

Looks at how Current_Light_Status and Current_Timer behave when AID is 1 versus 0, to understand patterns related to incidents.​

***Smart traffic insights***

Uses the features (speed, acceleration, light status, timer) and the Automatic Incident Detection (AID) flag to reason about potential traffic management rules, such as identifying abnormal speed drops or conditions where the signal timing may need adjustment.​

This workflow turns a raw CSV into interpretable information about traffic behavior at controlled intersections.

***Analysis goals***
The analysis in the notebook has three main goals:

Understand traffic behavior at intersections

Observe how speed and acceleration vary across different crossings and lanes.

Compare conditions when lights are in different states (L1, L3, etc.) and when timers are high or low.

Identify which lanes or crossings tend to have higher speeds or more variability in acceleration.

Explore conditions linked to incidents (AID = 1)

Examine the rows where AID is 1 and compare them with normal rows (AID = 0).

Look for patterns such as unusually low speeds, high acceleration spikes, or specific light states/timers that are associated with incidents.

Use these patterns to reason about potential threshold-based rules for early incident detection (for example, “if speed drops below X while timer and light status are Y, treat this as a risk condition”).

Support smart signal and management decisions

Use the relationship between Average_Speed, Average_Acceleration, Current_Light_Status, and Current_Timer to reason about how long certain lanes should remain green or red under different traffic conditions.

Highlight how dynamic adjustments could reduce congestion: for instance, giving more time to lanes that regularly show lower speeds or frequent AID events.

Provide an analytical foundation that could later be extended into a predictive or optimization model (for example, machine‑learning‑based incident prediction or adaptive signal control).

***Notebook workflow (conceptual)***
The notebook ties everything together with a clear data analysis pipeline:

Data loading and inspection: Reads STM.csv, checks the structure, and displays sample rows so that each column’s meaning is clear.

Cleaning and preparation: Ensures the data types and values are suitable for analysis (for example, converting time strings if needed, handling duplicates or missing values if they appear).

Descriptive statistics and visualization: Summarizes key features such as average speed and acceleration per crossing or lane, and explores how these change over time and across different light statuses.

Incident-focused exploration: Filters the dataset on AID = 1 to study what makes those records different from normal ones, helping to define possible rules for automatic incident detection.
