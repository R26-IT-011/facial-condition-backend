# Faceo Analytics — Facial Marks, Scars & Bruises Detection Microservice (YOLOv8 & YOLOv11)

Microservice running on default Port 8003 as part of the FACEO Facial Intelligence Platform.

## Features
- **Endpoint**: Microservice API for Facial Marks, Scars & Bruises Detection Microservice (YOLOv8 & YOLOv11)
- **Container**: Production-ready Dockerfile optimized for Google Cloud Run
- **Port**: Supports dynamic `$PORT` environment variable (defaults to 8003)
- **Cost**: Supports Scale-to-Zero (`min-instances = 0`) and request-based CPU allocation on GCP

## Local Run
```bash
pip install -r requirements.txt
python main.py
```

## Docker Build & Run
```bash
docker build -t facial-condition-backend .
docker run -p 8003:8003 -e PORT=8003 facial-condition-backend
```

## GCP Cloud Run Deployment
```bash
gcloud run deploy facial-condition-backend \
  --source . \
  --region asia-southeast1 \
  --min-instances 0 \
  --max-instances 1 \
  --memory 1Gi --cpu 1 \
  --cpu-throttling \
  --allow-unauthenticated
```
