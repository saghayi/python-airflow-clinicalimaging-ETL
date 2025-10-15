# python-airflow-clinical-imaging-ETL
A Python + Apache Airflow pipeline for ingesting, curating, and performing QC on medical imaging data (DICOM/NIfTI).

# Project Summary
A Python and Apache Airflow-based workflow for ingesting, curating, and performing QC on medical imaging data (DICOM/NIfTI).
The pipeline extracts metadata, performs validation, converts formats, and prepares data for ML or research analysis.

python-airflow-clinical-imaging-ETL/
│
├── README.md                     ← project overview
├── requirements.txt              ← Python dependencies
├── airflow/
│   └── dags/
│       └── dicom_ingestion_dag.py  ← Airflow DAG for automation
│
├── scripts/
│   ├── dicom_ingestion.py         ← raw ingestion script
│   ├── dicom_qc.py                ← QC and metadata validation
│   └── dicom_convert_nifti.py     ← convert DICOM → NIfTI
│
├── data/
│   ├── raw/                       ← raw DICOM data (sample or dummy)
│   ├── processed/                 ← processed and QCed data
│   └── logs/                      ← ingestion/QC logs
│
└── notebooks/
    └── analyze_metadata.ipynb     ← Jupyter notebook for EDA or visualization
