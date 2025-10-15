# python-airflow-clinical-imaging-ETL
A Python + Apache Airflow pipeline for ingesting, curating, and performing QC on medical imaging data (DICOM/NIfTI).

# Project Summary
A Python and Apache Airflow-based workflow for ingesting, curating, and performing QC on medical imaging data (DICOM/NIfTI).
The pipeline extracts metadata, performs validation, converts formats, and prepares data for ML or research analysis.

## Features
- Automated ingestion of DICOM files
- Metadata extraction (using `pydicom`)
- Basic QC validation (file integrity, completeness)
- Conversion to NIfTI format (using `nibabel`) for research/ML workflows
- Optional AWS S3 integration
- Airflow DAG orchestration

## Folder Structure
```pgsql
python-airflow-clinical-imaging-ETL/
│
├── README.md                     ← project overview
├── requirements.txt              ← Python dependencies
│
├── airflow/
│   └── dags/
│       └── dicom_ingestion_dag.py  ← Airflow DAG for automation
│
├── scripts/
│   ├── dicom_ingestion.py         ← raw ingestion script
│   ├── dicom_qc.py                ← QC and metadata validation
│   └── dicom_convert_nifti.py     ← convert DICOM → NIfTI
│   └── utils.py                    ← helper functions (logging, metadata, etc.)
│
├── data/
│   ├── raw/                       ← raw DICOM data (sample or dummy)
│   ├── processed/                 ← processed and QCed data
│   └── logs/                      ← ingestion/QC logs
│
└── notebooks/
    └── analyze_metadata.ipynb     ← Jupyter notebook for EDA or visualization

```

## Getting Started

1. **Clone the repository**
```bash
   git clone https://github.com/saghayi/python-airflow-clinicalimaging-ETL.git
   cd python-airflow-clinicalimaging-ETL
```

2. **Install dependencies**

```bash
pip install -r requirements.txt
```

3. ***Run ingestion script manually***

```bash
python scripts/dicom_ingestion.py
```

4. **(Optional) Run via Airflow**

- Copy the DAG to your Airflow dags folder
- Start Airflow and trigger the DAG manually or via schedule

## Example Output:
`data/logs/ingestion_log.csv` → stores metadata & QC summary

`data/processed/` → contains organized and converted imaging data


## Future consideration
- Add automated de-identification before conversion
- Store metadata in a database (e.g., Postgres or Snowflake)
- Expand QC checks (e.g., missing slices, resolution consistency)



