# Canopy Height Model (CHM) Tiled Visualization

This repository provides an interactive 3D visualization of forest canopy height models using pure JavaScript. The visualization enables users to explore forest structure across multiple CHM tiles, with an intuitive interface for analyzing canopy height data.

## Features

- **Interactive 3D CHM Visualization**: Navigate through a detailed 3D representation of forest canopy structure
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
  ```bash
   git clone https://github.com/klinucsd/of4d
   cd of4d/tools/chm
   ```
2. Copy visualization.html and OrbitControls.js to the folder in your web server
3. Download CHM tiles at SOAP from NEON at https://data.neonscience.org/data-products/DP3.30015.001
4. COPY the downlaoded CHM tiles at the same folder with visualization.html and OrbitControls.js

### Using Your Own CHM Data

The current implementation uses CHM tiles from the NEON SOAP site, but you can replace these with your own data:

1. Replace the GeoTIFF files referenced in the project
2. Update the `tileMetadata` array in the script to match your file names and UTM coordinates
3. Adjust the UTM zone in the `utmToLatLng` function if your data is in a different zone

## Data Format

The visualization expects GeoTIFF files with:
- Single-band raster data representing canopy height in meters
- Standard no-data values (-9999 or 65535)
- UTM coordinate system (default is zone 11)

## Controls

- **Left Mouse**: Rotate view
- **Right Mouse**: Pan view
- **Scroll Wheel**: Zoom in/out
- **H Key**: Toggle UI visibility
- **Control Panel**: Adjust visualization parameters
- **Map**: Click tiles to navigate

## Performance Considerations

The visualization dynamically loads and unloads tiles based on distance from the camera to maintain performance, even with numerous high-resolution tiles.

## License

This project is licensed under the MIT License.

## Acknowledgments

- [NEON (National Ecological Observatory Network)](https://www.neonscience.org/) for providing open CHM data
- Three.js, GeoTIFF.js, and other libraries that made this visualization possible
