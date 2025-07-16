# Environ

**Environ** is a web‑based geospatial platform for evaluating land parcels on environmental suitability and low‑impact urban development. It combines interactive 3D mapping, advanced environmental metrics, and a composite scoring engine to deliver actionable insights for architects, planners, consultants, developers, educators, and civic tech initiatives.

---

## 🔍 Key Features

- **Parcel Drawing & Analysis**  
  - Draw free‑form polygons or drop pins on a map  
  - Instant elevation, slope, runoff‑risk computation  

- **3D Sun‑Shadow Simulation**  
  - Real‑time shadows based on date, time, and season  
  - Interactive time‑slider control  

- **Multi‑Layer Environmental Metrics**  
  - **Runoff Risk:** Terrain and slope analysis via Elevation API  
  - **Noise Proxy:** Traffic‑based sound estimation  
  - **Canopy Coverage:** Tree‑cover density from OpenStreetMap  
  - **Walkability:** Amenity‑based scoring via Google Places  
  - **Transit Access:** Proximity to bus/train hubs  
  - **Climate Trends:** Historical temperature & rainfall  

- **Composite Suitability Score**  
  - Weighted aggregation of all sub‑scores  
  - Visual breakdown and overall rating (0–100)

- **User Accounts & Persistence**  
  - Firebase Authentication (email/OAuth)  
  - Save, load, and export parcel analyses  

- **Responsive & Performant**  
  - Optimized WebGL overlays for smooth 3D rendering  
  - Mobile‑first design for on‑the‑go assessments  

---

## 🏗 Architecture Overview

1. **Frontend** (Next.js + React)  
   - Interactive map canvas using Google Maps JavaScript API  
   - Three.js WebGLOverlayView for custom 3D shadows  
   - Tailwind CSS + ShadCN UI for consistent styling  

2. **Backend** (Node.js + Express)  
   - `/api/score` – Aggregates all metric services and returns a structured `SuitabilityScore` JSON  
   - `/api/parcels` – CRUD endpoints for user‑saved parcel data  
   - Authentication middleware validating Firebase tokens  

3. **Data & Services**  
   - **Google Elevation API** for terrain analysis  
   - **Google Places + Distance Matrix** for walkability & transit  
   - **OpenStreetMap** for canopy coverage  
   - **Open‑Meteo / NOAA** for climate history  
   - Custom traffic‑based noise proxy algorithm  

4. **Persistence**  
   - MongoDB Atlas for parcel storage  
   - Firebase Auth for user management  
