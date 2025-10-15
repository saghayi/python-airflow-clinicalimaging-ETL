# python-airflow-clinical-imaging-ETL
A Python + Apache Airflow pipeline for ingesting, curating, and performing QC on medical imaging data (DICOM/NIfTI).

# Project Summary
A Python and Apache Airflow-based workflow for ingesting, curating, and performing QC on medical imaging data (DICOM/NIfTI).
The pipeline extracts metadata, performs validation, converts formats, and prepares data for ML or research analysis.

## Features
- Automated ingestion of DICOM files
- Metadata extraction and QC validation
- Conversion to NIfTI format for research/ML workflows
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
