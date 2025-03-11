## The documentation for the datasets and metadata released under  **[Malware Detection In the Wild Leaderboard](https://malwaredetectioninthewild.github.io/)** [See our SaTML 2025 paper](https://arxiv.org/abs/2405.06124)

We prepared two datasets to release to the community, please read carefully for details and participation rules.

1. **Train Data** (`MalwareITW_TrainData.zip`): This dataset includes only the sandbox traces for the samples first seen on VirusTotal before the training cut-off timestamp we used in our paper (`1522540800`, April 1st, 2018). We used this timestamp to split our training and testing sets. This dataset also includes the metadata for both sandbox and endpoint samples in the training split. **If you wish to participate in our leaderboard for realistic evaluations, you must request access to this dataset**. We are releasing a small subset of this dataset in this repository (`MalwareITW_TrainData_Sample.zip`). This sample has the same directory structure as the full Train data.

<br>

2. **TrainAndTest Data** (`MalwareITW_TrainAndTestData.zip`): This dataset includes all the sandbox traces we used in our paper and the metadata for all samples (both sandbox and endpoint samples). **If granted access to this dataset, you can no longer submit to our leaderboard**. We are releasing a small subset of this dataset in this repository (`MalwareITW_TrainAndTestData_Sample.zip`). This sample has the same directory structure as the full TrainAndTest data.

---

### Included Files

Please download and extract `MalwareITW_TrainData_Sample.zip` (or `MalwareITW_TrainData.zip`) and  `MalwareITW_TrainAndTestData_Sample.zip` (or `MalwareITW_TrainAndTestData.zip`) into the repository directory.

#### Metadata files:

We provide `ReadMetadata.ipynb` notebook to explore and describe the metadata format. This demonstrates how to obtain ground truth labels, family labels, and publisher labels (along with the labeling timestamps) from our metadata.

##### **Train Data**

* `MalwareITW_TrainData_Sample/Train_sandbox_metadata.json` (this is `MalwareITW_TrainData/Train_sandbox_metadata.json` for the full Train Data). This contains the metadata for the sandbox samples in the training split.

* `MalwareITW_TrainData_Sample/Train_endpoint_metadata.json` (this is `MalwareITW_TrainData/Train_endpoint_metadata.json` for the full Train Data). This contains the metadata for the endpoint samples in the training split.

##### **TrainAndTest Data**

* `MalwareITW_TrainAndTestData_Sample/TrainAndTest_sandbox_metadata.json` (this is `MalwareITW_TrainAndTestData/TrainAndTest_sandbox_metadata.json` for the full TrainAndTest Data). This contains the metadata for all sandbox samples in our paper.

* `MalwareITW_TrainAndTestData_Sample/TrainAndTest_endpoint_metadata.json` (this will be `MalwareITW_TrainAndTestData/TrainAndTest_endpoint_metadata.json` for the full TrainAndTest Data). This contains the metadata for all endpoint samples in our paper.

--- 

#### Execution Traces Files

Our sandbox traces dataset includes traces from two sandboxes labeled `Habo` and `Cuckoo`.

Each trace is stored as a `<hash>.json` file that contains the trace from the sample with the SHA-256 hash of `<hash>`.

We provide `StandardizedDataFormat.ipynb` notebook to explain the trace format used in our sandbox and endpoint datasets. Participants are expected to provide detectors that can take traces in our `.json` format as input to make predictions (i.e., output a predicted probability score of whether the trace belongs to a malware sample).

##### **Train Data**

`MalwareITW_TrainData_Sample\sandbox_dataset` (and the full Train Data `MalwareITW_TrainData\sandbox_dataset`) have the following directory structure:

- `sandbox_dataset`
    - `Train`
        - `Habo`
            - `0d0460726570d9ff0a412ed0d4ddca87a8a3fa6c7cda1059c4477e17f17f5ff6.json` 
        - `Cuckoo`
            - `8c83ea264e7d99612ac9e28885187fad7df58e61778af8727d6bf78f43970a9b.json`

##### **TrainAndTest Data**

`MalwareITW_TrainAndTestData_Sample\sandbox_dataset` (and the full TrainAndTest Data `MalwareITW_TrainAndTestData\sandbox_dataset`) have the following directory structure:

- `sandbox_dataset`
    - `Train`
        - `Habo`
            - `0d0460726570d9ff0a412ed0d4ddca87a8a3fa6c7cda1059c4477e17f17f5ff6.json` 
        - `Cuckoo`
            - `8c83ea264e7d99612ac9e28885187fad7df58e61778af8727d6bf78f43970a9b.json`
    - `Test`
        - `Habo`
            - `1dbe1e28967cfe49c830cdb73ff0ac7ab4a773bbd20f1bfe031f58edd414bb57.json` 
        - `Cuckoo`
            - `7ce80babf46d0ecc30ed9b2e9292d3d3d988325bb0fdc971d867509569617a67.json`

Note how the TrainAndTest Data includes another subdirectory named `Test`.

---

### Request Access

To request access to our data please contact [Yigitcan Kaya](https://yigitcankaya.github.io) at **yigitcan at ucsb dot edu**

Please use the subject line `MalwareITW Data Request: Train Data` or `MalwareITW Data Request: TraindAndTest Data` for your emails. Make sure to include your name and institution in the body of your email. 

**If granted access to the TraindAndTest Data, you can no longer submit to our leaderboard**. This ensures that the detectors submitted to the leaderboard are realistic and obey causality (trained on samples that existed before the testing samples). Moreover, the metadata in the TraindAndTest Data also includes the endpoint samples in our testing split, on which the submitted models will be evaluated. 

Once you download the dataset, extract the `.zip` file, to create `MalwareITW_TrainData` (or `MalwareITW_TrainAndTestData`). This will create the directories described in our tutorial.

---

### **Institutions that were granted access to the dataset (sorted by request date):**
