# Canopy Height Model (CHM) Tiled Visualization

This repository provides an interactive 3D visualization of forest canopy height models using pure JavaScript. The visualization enables users to explore forest structure across multiple terrain tiles, with an intuitive interface for analyzing canopy height data.

## Features

- **Interactive 3D Terrain Visualization**: Navigate through a detailed 3D representation of forest canopy structure
- **Multi-tile Support**: Seamlessly loads and visualizes multiple CHM GeoTIFF tiles
- **Height-based Coloring**: Visual gradient representing canopy heights
- **Interactive Map**: Minimap for easy navigation between tiles
- **Data Analysis**: Height distribution charts for selected tiles
- **Customizable Settings**:
  - Height exaggeration adjustment
  - Wireframe mode
  - Smooth/flat shading
  - Minimum height filtering

## Live Demo

[View the live demo](https://of4d-beta.sdsc.edu/chm/visualization.html)

## How It Works

The visualization uses Three.js to render GeoTIFF canopy height data as 3D terrain. Each CHM tile is processed into a 3D mesh with vertex heights corresponding to canopy heights, and colors mapped to a gradient scale. A minimap using Leaflet helps with navigation between tiles.

### Technical Components

- **Three.js**: 3D rendering of terrain data
- **GeoTIFF.js**: Reading and parsing GeoTIFF canopy height files
- **dat.GUI**: Interactive controls panel
- **Leaflet**: Overview map for tile selection
- **Proj4js**: Coordinate transformation between UTM and WGS84
- **Chart.js**: Height distribution analysis

## Getting Started

### Prerequisites

No build tools required! This project uses CDN-loaded libraries for simplicity.

### Installation

1. Clone the repository

git clone [https://github.com/klinucsd/of4d]

cd tools/chm/visualization

2. 
