# 🗺️ RealMap TSP — Bursa Tour Optimization

**Project:** Minimum Distance Traveling Salesperson Problem (TSP) on Real Street Networks  
**Location:** Osmangazi, Bursa, Türkiye  

---

## 📘 Overview

This project solves a **real-world Traveling Salesperson Problem (TSP)** over the **actual road network of Bursa** using **OpenStreetMap data**.  
By applying the **Greedy Insertion heuristic**, the algorithm computes the **shortest possible driving route** that visits all selected tourist landmarks exactly once and returns to the starting point.

The final results include:
- ✅ Optimized route sequence  
- 📏 Total driving distance and estimated travel time  
- 🗺️ Interactive map visualization (`Bursa_tsp_min_distance_final_map.html`)

---

## 🧩 Methodology

### 1️⃣ Data Acquisition
- The project uses **OSMnx** to download the real street network of **Osmangazi, Bursa**.  
- The network type is set to `drive`, ensuring **directed edges** (e.g., one-way streets) are respected.  
- Each landmark is mapped to the **nearest valid road node** on the map.

### 2️⃣ TSP Formulation
- Each landmark pair is connected using **Dijkstra’s shortest path algorithm** from `networkx`.  
- A **cost matrix** of all inter-landmark distances is computed.  
- The **Greedy Insertion** heuristic minimizes the total distance by inserting each new stop into the current tour at the point of least cost increase:

\[
\Delta C(i, k, j) = d(i, k) + d(k, j) - d(i, j)
\]

### 3️⃣ Optimization Results
- **Route Sequence:**  
  `Ulu Camii → Muradiye Külliyesi → Lunapark → Tophane Saat Kulesi → Koza Han → Panorama 1326 Bursa Fetih Müzesi → Irgandı Köprüsü → Hünkar Köşkü → Saltanat Kapısı → Ulu Camii`  
- **Total Distance:** 12.99 km  
- **Estimated Duration (30 km/h):** 25 minutes 58 seconds  

### 4️⃣ Visualization
- The optimized route is visualized interactively using **Folium**.  
- The HTML map includes:
  - 🔴 Red polyline for the route  
  - 🔵 Numbered blue markers for stops  
  - 📋 A summary box with total distance and duration  

---

## 🧠 Key Technologies

| Library | Purpose |
|----------|----------|
| **osmnx** | Download and process real street network data |
| **networkx** | Graph operations and shortest path computation |
| **numpy** | Matrix and numerical calculations |
| **folium** | Interactive route visualization |
| **datetime** | Travel time estimation |

