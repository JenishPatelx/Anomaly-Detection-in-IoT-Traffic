Project Highlights
Dataset: Uses a reduced version of the IoT-23 dataset.
Goal: Train and test models to distinguish between normal and malicious IoT network behavior.
Outputs:
Preprocessed data tailored for ML pipelines.
Trained models stored for reuse.
Visualizations of performance metrics and experimental results.
Getting Started
Requirements
Before running the project, ensure you have the following tools and libraries installed:

Tool/Library	Version	Purpose
Python	3.8.8	Programming Language
scikit-learn	0.24.1	Machine learning framework
NumPy	1.19.5	Numerical operations and array handling
pandas	1.2.2	Data manipulation and analysis
Matplotlib	3.3.4	Plotting and visualization
Seaborn	0.11.1	Statistical data visualization
psutil	5.8.0	System monitoring and resource tracking
scikit-plot	0.3.7	Easy-to-use visualizations for scikit-learn
pickle	Built-in	Model serialization and deserialization
Install the dependencies using:

bash
Copy code
pip install -r requirements.txt  
Dataset Setup
Download: Get the lightweight version of the IoT-23 dataset (~8.8 GB) from here.
Extract: Unzip the dataset, which will expand to approximately 44 GB.
How to Use
1. Configuration
Clone the repository:

bash
Copy code
git clone <repository_url>  
cd <repository_directory>  
Open config.py and configure the paths:

iot23_scenarios_dir: Directory where IoT-23 scenarios are stored.
iot23_attacks_dir: Directory for segregated attack data.
iot23_data_dir: Directory for processed data.
iot23_experiments_dir: Directory to store results, charts, and trained models.
Verify the setup:

bash
Copy code
python run_step00_configuration_check.py  
Ensure there are no errors before proceeding.

2. Data Preprocessing
Step 1: Extract Relevant Data
Run the script to parse raw scenario files and segregate benign and malicious traffic:

bash
Copy code
python run_step01_extract_data_from_scenarios.py  
Output: Attack-specific data stored in iot23_attacks_dir.
Duration: ~2 hours.
Step 2: Shuffle and Partition Data
Improve data reliability by shuffling and partitioning large files:

bash
Copy code
python run_step01_shuffle_file_content.py  
Large files (>1 GB) are partitioned, shuffled, and merged.
Duration: ~3 hours.
3. Running Experiments
Option 1: Quick Demo
Run a small-scale experiment using a subset of the data to ensure the setup is working correctly:

bash
Copy code
python run_demo.py  
Processes only 10,000 records per file.
Execution Time: A few minutes.
Option 2: Full Experiment
Run the complete training and testing pipeline with all records:

bash
Copy code
python run_experiments.py  
Dataset Size: Over 20 million records.
Execution Time: ~24 hours.
Option 3: Custom Experiment
Design your own experiment by modifying parameters and datasets in the scripts:

bash
Copy code
python run_custom_experiment.py  