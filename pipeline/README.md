📦 NYC Taxi Data Pipeline

Simple data pipeline to ingest NYC Yellow Taxi data into PostgreSQL using Python and Docker.


🧱 Architecture
	•	PostgreSQL runs inside Docker
	•	Python script downloads NYC Yellow Taxi dataset
	•	Data is loaded into PostgreSQL using SQLAlchemy


Flow:
NYC Taxi CSV → Python ingestion → PostgreSQL (Docker)

🛠 Tech Stack
	•	Python
	•	PostgreSQL
	•	Docker
	•	SQLAlchemy
	•	psycopg


🚀 Setup

1️⃣ Start PostgreSQL (Docker)
If using Docker:
```bash
docker run -it \
  -e POSTGRES_USER=root \
  -e POSTGRES_PASSWORD=root \
  -e POSTGRES_DB=ny_taxi \
  -p 5432:5432 \
  postgres:15
```


2️⃣ Install Dependencies
Using uv:
uv sync

Or pip:
pip install -r requirements.txt

▶️ Run Ingestion
```bash
python ingest_data.py
```

This will:
	•	Download January 2021 Yellow Taxi data
	•	Create table yellow_taxi_data
	•	Insert data in chunks