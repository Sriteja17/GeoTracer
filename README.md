# GeoTrace

**GeoTrace** is an AI-powered geospatial intelligence system that extracts location information from images, analyzes movement patterns, identifies frequently visited locations, and presents the results through an interactive dashboard.

The project demonstrates a complete end-to-end geospatial intelligence pipeline, beginning with raw images and ending with an interactive visualization of movement behavior.

---

# Features

* Extract GPS coordinates and timestamps from image EXIF metadata
* Fallback location estimation using Computer Vision when EXIF data is unavailable
* Store extracted metadata in a local SQLite database
* Cluster geographical locations using the DBSCAN clustering algorithm
* Detect frequently visited places and movement hotspots
* Analyze movement trajectories and travel behavior
* Compute:

  * Total travel distance
  * Movement speed
  * Dwell time
  * Time-of-day activity
  * Movement corridors
  * Behavioral classification
* Generate an interactive dashboard with:

  * Dynamic map visualization
  * Heatmap overlay
  * Route visualization
  * Privacy exposure analysis
  * Exportable CSV reports

---

# Project Pipeline

```
Images
   │
   ▼
Metadata Preprocessing
   │
   ▼
Location Clustering
   │
   ▼
Movement Intelligence
   │
   ▼
Interactive Dashboard
```

---

# System Architecture

```
                    Images
                       │
                       ▼
         Metadata Preprocessing
     (EXIF + Vision Location Recovery)
                       │
                       ▼
             SQLite Metadata Store
                       │
                       ▼
               GPS Point Dataset
                       │
                       ▼
           DBSCAN Spatial Clustering
                       │
                       ▼
          Movement Intelligence Engine
                       │
        ┌──────────────┼──────────────┐
        │              │              │
        ▼              ▼              ▼
   Dwell Time     Speed Analysis   Corridors
        │
        ▼
   Intelligence Report
        │
        ▼
 Interactive Dashboard
```

---

# Technologies Used

## Programming Language

* Python 3.x

## Computer Vision

* Pillow (PIL)

## Data Processing

* NumPy
* JSON
* SQLite3

## Machine Learning

* Scikit-learn
* DBSCAN Clustering

## Geospatial Libraries

* Folium
* Leaflet.js
* HeatMap Plugin
* Polyline
* Haversine Formula

## Web Technologies

* HTML5
* CSS3
* JavaScript

---

# Folder Structure

```text
GeoTrace/
│
├── app.py
├── README.md
│
├── Clusturing
│   ├── cluster.py
│   ├── clusters.json
│   ├── points_with_clusters.json
│   └── __init__.py
│
├── Dashboard
│   ├── dashboard.html
│   ├── map.html
│   └── member4_dashboard.py
│
├── Metadata Preprocessing
│   ├── database.py
│   ├── exif_utils.py
│   ├── main.py
│   ├── metadata.db
│   ├── output_data.json
│   ├── test.py
│   └── vision_utils.py
│
└── Movement Analysis
    ├── intelligence.json
    ├── member3_movement.py
    └── __init__.py
```

---

# Module Overview

## 1. Metadata Preprocessing

Responsible for extracting location information from input images.

### Functions

* Read EXIF metadata
* Extract GPS coordinates
* Extract timestamps
* Recover missing GPS using Vision API
* Store metadata inside SQLite
* Export processed metadata to JSON

**Output**

```
output_data.json
```

---

## 2. Clustering

Processes extracted GPS coordinates using DBSCAN.

### Functions

* Spatial clustering
* Noise detection
* Cluster centroid calculation
* Movement radius computation

**Outputs**

```
clusters.json

points_with_clusters.json
```

---

## 3. Movement Analysis

Generates movement intelligence from clustered locations.

### Features

* Point-to-point distance
* Speed estimation
* Movement corridors
* Dwell time analysis
* Time-of-day profiling
* Behavioral classification
* Summary statistics

**Output**

```
intelligence.json
```

---

## 4. Dashboard

Visualizes the complete intelligence report.

### Features

* Interactive map
* Heatmap
* Route visualization
* Cluster information
* Statistics dashboard
* Privacy exposure score
* CSV export

---

# Data Flow

```
Images
      │
      ▼
Metadata Extraction
      │
      ▼
SQLite Database
      │
      ▼
output_data.json
      │
      ▼
DBSCAN Clustering
      │
      ▼
clusters.json
points_with_clusters.json
      │
      ▼
Movement Analysis
      │
      ▼
intelligence.json
      │
      ▼
Dashboard
```

---

# Installation

Clone the repository

```bash
git clone https://github.com/your-username/GeoTrace.git

cd GeoTrace
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

# Running the Project

Run the complete pipeline

```bash
python app.py
```

Or execute each stage individually

### Metadata Extraction

```bash
python "Metadata Preprocessing/main.py"
```

### Clustering

```bash
python Clusturing/cluster.py
```

### Movement Analysis

```bash
python "Movement Analysis/member3_movement.py"
```

### Dashboard

```bash
python Dashboard/member4_dashboard.py
```

Open

```
Dashboard/dashboard.html
```

in your browser.

---

# Outputs Generated

| File                      | Description                       |
| ------------------------- | --------------------------------- |
| output_data.json          | Extracted metadata from images    |
| metadata.db               | SQLite metadata database          |
| clusters.json             | Cluster summaries                 |
| points_with_clusters.json | GPS points with assigned clusters |
| intelligence.json         | Movement intelligence report      |
| map.html                  | Interactive map                   |
| dashboard.html            | Dashboard interface               |

---

# Future Improvements

* Real-time GPS tracking
* Live dashboard updates
* Person re-identification
* Face anonymization
* Multi-user support
* Temporal anomaly detection
* Predictive movement modeling
* Cloud deployment
* Mobile application
* REST API integration

---

# Team Contributions

### Metadata Preprocessing

* Image metadata extraction
* EXIF processing
* Vision-based GPS recovery
* SQLite storage

### Clustering

* Spatial clustering
* Hotspot detection
* Cluster summarization

### Movement Analysis

* Behavioral intelligence
* Speed analysis
* Dwell time estimation
* Movement corridor detection

### Dashboard

* Interactive visualization
* Analytics dashboard
* Heatmaps
* Privacy exposure scoring

---

# License

This project is developed for educational and research purposes.
