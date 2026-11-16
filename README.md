# 🚇 Metro Route Navigation System

An interactive desktop-based Metro Route Navigation System built using **C++17 and Qt 6**, implementing graph algorithms to find optimal metro routes, visualize algorithm execution, and analyze network resilience under simulated station and track failures.

The system models a metro network as a weighted, undirected graph and provides multiple route-finding strategies through an interactive graphical interface.

---

## 📌 Overview

The Metro Route Navigation System helps users navigate a sample metro network by finding routes between stations based on different optimization criteria.

Beyond basic navigation, the application provides an interactive environment to understand how graph algorithms work, visualize their execution step by step, simulate network disruptions, and manage metro connections.

The project uses a sample network of **17 stations and 21 tracks across 5 metro lines**, loosely inspired by the Delhi Metro.

## ✨ Key Features

### 1. Metro Navigator
- Select source and destination stations through dropdowns or directly from the map.
- Find the **fastest route** using Dijkstra's Algorithm.
- Find the route with the **fewest stops** using Breadth-First Search (BFS).
- View total travel time, number of stops, and interchanges.
- Visualize the selected route on the metro map.
- View a step-by-step journey timeline with line-change information.

### 2. Algorithm Visualizer
- Interactive visualization of Dijkstra's Algorithm, BFS, and DFS.
- Step-by-step execution with playback controls.
- View visited stations and traversal order.
- Track distance tables, parent relationships, and queue/stack contents.
- Compare the results of all three algorithms for the same source-destination pair.

### 3. Network Resilience Lab
- Simulate station and track failures by clicking directly on the map.
- Identify disconnected components in the network.
- Detect critical stations (Articulation Points).
- Detect critical tracks (Bridges) using Tarjan's Algorithm.
- Visualize failed stations, failed tracks, and critical network elements.
- Restore individual failures or reset the entire network.
- Analyze journey availability under different failure conditions.

### 4. Station Management
- Add new connections between existing stations.
- Remove existing tracks.
- Delete stations and their associated connections.
- Search and browse the station directory.
- Automatically refresh the map and navigation options after modifications.

---

## 🧠 Algorithms & Data Structures

The project demonstrates the practical application of fundamental graph algorithms and data structures.

| Algorithm | Purpose | Time Complexity |
|---|---|---|
| Dijkstra's Algorithm | Fastest route | O((V + E) log V) |
| Breadth-First Search (BFS) | Fewest stops | O(V + E) |
| Depth-First Search (DFS) | Find any valid route | O(V + E) |
| Tarjan's Algorithm | Find bridges and articulation points | O(V + E) |
| BFS | Find connected components | O(V + E) |

### Data Structures Used

- **Adjacency Lists:** Graph representation.
- **Hash Maps:** Station registries, distances, parents, and discovery tables.
- **Priority Queue (Min-Heap):** Efficient selection of the minimum-distance station in Dijkstra's Algorithm.
- **Queues:** BFS traversal and connected component detection.
- **Recursion:** DFS and Tarjan's Algorithm.
- **Hash Sets:** Visited stations and failed network elements.
- **Sorted Sets:** Maintaining unique metro line information.

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| C++17 | Core application logic and algorithms |
| Qt 6 Widgets | Graphical user interface |
| Standard Template Library (STL) | Data structures and algorithm implementation |
| QMake | Build configuration |
| MinGW | C++ compiler |
| Qt Creator | Development environment |
| SQL (MySQL syntax) | Relational database schema and seed data |

---

## 🏗️ System Architecture

The application follows a layered architecture:

1. **Presentation Layer:** Handles the graphical interface, map rendering, navigation, visualization, and user interactions.
2. **Logic Layer:** Implements graph algorithms, visualization execution, and network resilience analysis.
3. **Data Layer:** Maintains the metro graph, station and track registries, and relational schema.

### Major Components

| Component | Responsibility |
|---|---|
| `MetroGraph` | Graph representation and failure management |
| `GraphAlgorithms` | Dijkstra, BFS, DFS, and route reconstruction |
| `VisualizerEngine` | Records and replays algorithm execution steps |
| `ResilienceEngine` | Connected components, bridges, and articulation points |
| `MetroMapView` | Custom metro map rendering and mouse interactions |
| `MainWindow` | Main application interface |
| `NavigatorPage` | Route selection and journey summary |
| `VisualizerPage` | Algorithm playback and comparison |
| `ResiliencePage` | Failure simulation and network analysis |
| `ManagementPage` | Station and track management |
| `AppTheme` | Application styling and color configuration |

---

## 📊 Sample Results

For a journey from **Dwarka to Noida Sector**, the three algorithms produce different results depending on their objectives.

| Algorithm | Travel Time | Stops | Interchanges |
|---|---:|---:|---:|
| Dijkstra | 25 min | 7 | 1 |
| BFS | 44 min | 4 | 0 |
| DFS | 46 min | 11 | 4 |

This demonstrates that the route with the fewest stops is not necessarily the fastest route.

### Network Resilience Testing

The system was also tested under different station and track failure scenarios.

For example:
- Closing Rajiv Chowk keeps the network connected but increases its vulnerability.
- Closing Janakpuri disconnects Dwarka from the rest of the network.
- Failing the Dwarka–Janakpuri track similarly isolates Dwarka.
- Simultaneously closing Rajiv Chowk and Saket significantly increases the number of critical stations and tracks.

---

## 📁 Project Scope

The current implementation includes:
- 17 metro stations.
- 21 metro connections.
- 5 metro lines: Blue, Yellow, Orange, Green, and Pink.
- Weighted, undirected graph representation.
- Interactive route navigation and algorithm visualization.
- Network failure simulation and resilience analysis.

**Note:** The current application loads its sample network into memory. Although a relational database schema and SQLite seed database have been prepared, database integration with the running application is not yet implemented. Station and track modifications are therefore not persisted after closing the application.

---

## 🚀 Future Improvements

- Integrate the database for persistent station and track modifications.
- Add new station creation and map positioning.
- Introduce interchange penalties and realistic train timetables.
- Implement A* search for more efficient navigation on larger networks.
- Display alternative routes, including second and third-best options.
- Incorporate metro fares and station facilities into journey planning.

---

## 👥 Contributors

Developed as part of the B.Tech Computer Science and Engineering curriculum at **Jaypee Institute of Information Technology, Noida**.

| Name | Enrolment Number |
|---|---|
| Dhairya Khandelwal | 2501030058 |
| Aditya Vishoriya | 2501030054 |
| Ekansh Girdhar | 2501030050 |

**Department:** Computer Science and Engineering  
**Semester:** 3rd Semester

---

## 📚 References

- Introduction to Algorithms — Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, and Clifford Stein.
- E. W. Dijkstra, *A Note on Two Problems in Connexion with Graphs*, 1959.
- R. E. Tarjan, *Depth-First Search and Linear Graph Algorithms*, 1972.
- [Qt 6 Documentation](https://doc.qt.io/)
- [C++ Reference](https://en.cppreference.com/)

---

<p align="center">
  <b>Built with C++17, Qt 6, and Graph Algorithms.</b><br>
  Exploring the intersection of Data Structures, Algorithms, and Real-World Systems.
</p>
