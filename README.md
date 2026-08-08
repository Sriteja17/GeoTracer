# 🌍GeoTracer

**GeoTrace** is an AI-powered geospatial intelligence system that extracts location information from images, analyzes movement patterns, identifies frequently visited locations, and presents the results through an interactive dashboard.

The project demonstrates a complete end-to-end geospatial intelligence pipeline — from raw images to an interactive visualization of movement behavior.

---

## Table of Contents

- [Features](#features)
- [Project Pipeline](#project-pipeline)
- [System Architecture](#system-architecture)
- [Technologies Used](#technologies-used)
- [Folder Structure](#folder-structure)
- [Module Overview](#module-overview)
- [Data Flow](#data-flow)
- [How to Run](#how-to-run)
- [Outputs Generated](#outputs-generated)
- [Future Improvements](#future-improvements)
- [Team Contributions](#team-contributions)
- [License](#license)

---

## ✨Features

- Extract GPS coordinates and timestamps from image EXIF metadata
- Fallback location estimation using Computer Vision when EXIF data is unavailable
- Store extracted metadata in a local SQLite database
- Cluster geographical locations using the DBSCAN clustering algorithm
- Detect frequently visited places and movement hotspots
- Analyze movement trajectories and travel behavior, including:
  - Total travel distance
  - Movement speed
  - Dwell time
  - Time of day activity
  - Movement corridors
  - Behavioral classification
- Generate an interactive dashboard with:
  - Dynamic map visualization
  - Heatmap overlay
  - Route visualization
  - Privacy exposure analysis
  - Exportable CSV reports

---

## 🔄Project Pipeline

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

## 🏗️System Architecture

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

## 🛠️Technologies Used

| Category | Tools / Libraries |
|---|---|
| **Programming Language** | Python 3.x |
| **Computer Vision** | Pillow (PIL) |
| **Data Processing** | NumPy, JSON, SQLite3 |
| **Machine Learning** | Scikit-learn, DBSCAN Clustering |
| **Geospatial Libraries** | Folium, Leaflet.js, HeatMap Plugin, Polyline, Haversine Formula |
| **Web Technologies** | HTML5, CSS3, JavaScript |

---

## 📁Folder Structure

```
GeoTrace/
│
├── app.py
├── README.md
│
├── Clusturing/
│   ├── cluster.py
│   ├── clusters.json
│   ├── points_with_clusters.json
│   └── __init__.py
│
├── Dashboard/
│   ├── dashboard.html
│   ├── map.html
│   └── member4_dashboard.py
│
├── Metadata Preprocessing/
│   ├── database.py
│   ├── exif_utils.py
│   ├── main.py
│   ├── metadata.db
│   ├── output_data.json
│   ├── test.py
│   └── vision_utils.py
│
└── Movement Analysis/
    ├── intelligence.json
    ├── member3_movement.py
    └── __init__.py
```

---

## 🧩Module Overview

### 1️⃣ Metadata Preprocessing

Responsible for extracting location information from input images.

**Functions**
- Read EXIF metadata
- Extract GPS coordinates
- Extract timestamps
- Recover missing GPS using Vision API
- Store metadata inside SQLite
- Export processed metadata to JSON

**Output:** `output_data.json`

### 2️⃣ Clustering

Processes extracted GPS coordinates using DBSCAN.

**Functions**
- Spatial clustering
- Noise detection
- Cluster centroid calculation
- Movement radius computation

**Outputs:** `clusters.json`, `points_with_clusters.json`

### 3️⃣ Movement Analysis

Generates movement intelligence from clustered locations.

**Features**
- Point-to-point distance
- Speed estimation
- Movement corridors
- Dwell time analysis
- Time-of-day profiling
- Behavioral classification
- Summary statistics

**Output:** `intelligence.json`

### 4️⃣ Dashboard

Visualizes the complete intelligence report.

**Features**
- Interactive map
- Heatmap
- Route visualization
- Cluster information
- Statistics dashboard
- Privacy exposure score
- CSV export

---

## 🔀Data Flow

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
clusters.json / points_with_clusters.json
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

## 🚀How to Run

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/GeoTrace.git
cd GeoTrace
```

### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 3️⃣ Add Images

Place all images you want to analyze inside the `images/` folder.

```
images/
├── image1.jpg
├── image2.jpg
├── image3.jpg
```

The images may contain:
- GPS EXIF metadata
- Timestamp metadata
- Or neither (Vision API fallback will be used)

### 4️⃣ Run the Entire Pipeline

```bash
python app.py
```

The application automatically executes every stage in sequence:

```
Images → Metadata Extraction → SQLite Database → DBSCAN Clustering → Movement Analysis → Dashboard Generation
```

### 5️⃣ Run Individual Modules (Optional)

If you'd rather execute each stage independently:

**Metadata Extraction**
```bash
python "Metadata Preprocessing/main.py"
```

**Clustering**
```bash
python Clusturing/cluster.py
```

**Movement Analysis**
```bash
python "Movement Analysis/member3_movement.py"
```

**Dashboard**
```bash
python Dashboard/member4_dashboard.py
```

### 6️⃣ View the Dashboard

Open `Dashboard/dashboard.html` in your preferred web browser. The dashboard provides:
- Interactive movement map
- Cluster visualization
- Heatmap
- Movement statistics
- Privacy exposure score
- CSV export

---

## 📦Outputs Generated

| File | Description |
|---|---|
| `output_data.json` | Extracted metadata from images |
| `metadata.db` | SQLite metadata database |
| `clusters.json` | Cluster summaries |
| `points_with_clusters.json` | GPS points with assigned clusters |
| `intelligence.json` | Movement intelligence report |
| `map.html` | Interactive map |
| `dashboard.html` | Dashboard interface |

---

## 🔮Future Improvements

- Real-time GPS tracking
- Live dashboard updates
- Person re-identification
- Face anonymization
- Multi-user support
- Temporal anomaly detection
- Predictive movement modeling
- Cloud deployment
- Mobile application
- REST API integration

---

## 👥Team Contributions

**Metadata Preprocessing**
- Image metadata extraction
- EXIF processing
- Vision-based GPS recovery
- SQLite storage

**Clustering**
- Spatial clustering
- Hotspot detection
- Cluster summarization

**Movement Analysis**
- Behavioral intelligence
- Speed analysis
- Dwell time estimation
- Movement corridor detection

**Dashboard**
- Interactive visualization
- Analytics dashboard
- Heatmaps
- Privacy exposure scoring

**Contributors**
- [Anirudh Chavali](https://github.com/anirudh110106)
- [Bommalakunta Anish Kumar](https://github.com/Anish1817)
- [Kodam Sriteja](https://github.com/Sriteja17)
- [Shaik Yunis](https://github.com/Yunis147)

---

## 📄License

This project is developed for educational and research purposes.
