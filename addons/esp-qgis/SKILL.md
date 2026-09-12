---
name: esp-qgis
description: >-
  Comprehensive QGIS MCP automation skill for executing spatial analysis,
  geoprocessing, and map manipulation using PyQGIS and the WAI QGIS MCP plugin.
---

# QGIS Automation & Spatial Analysis (esp-qgis)

<esper_module type="skill">
<purpose>
Provide agents with the exact workflow, initialization steps, and structural rules needed to interface with QGIS via the `qgis-mcp` bridge and the `WAI QGIS MCP` plugin.
</purpose>
<when_to_use>
<item>When the user asks to perform spatial analysis or geoprocessing</item>
<item>When the project involves shapefiles, geojson, or spatial databases</item>
<item>When the user needs to automate QGIS mapping tasks</item>
</when_to_use>

<instructions>

## 1. Initialization & Pre-Flight Checks
Before attempting any spatial analysis, you must ensure the QGIS MCP bridge is correctly configured.
- **Dependency Check**: Verify `uv` or `npm` is installed on the user's system.
- **MCP Config**: Ensure `~/.gemini/config/mcp_config.json` contains the following server config:
  ```json
  "qgis-mcp": {
    "command": "uvx",
    "args": ["--from", "https://github.com/nkarasiak/qgis-mcp/archive/refs/heads/main.zip", "qgis-mcp-server"]
  }
  ```
- **User Instruction**: Remind the user to open QGIS, install the experimental **WAI QGIS MCP** plugin via the Plugin Manager, and click "Start Server".

## 2. Core Spatial Principles
When writing PyQGIS code for the `qgis_execute_code` tool, you MUST adhere to strict spatial rules:
1. **Coordinate Reference Systems (CRS) Awareness**: Strictly differentiate between a Geographic Coordinate System (GCS, e.g., EPSG:4326) and a Projected Coordinate System (PCS, e.g., UTM Zones).
2. **Unit Handling**:
   - EPSG:4326 units are **Degrees** (Latitude/Longitude).
   - EPSG:327xx units are **Meters** (X/Y).
3. **No Geographical Buffering**: **NEVER** execute distance-based geoprocessing tools (buffers, area calculations, distances) on a Geographic CRS. You MUST reproject the data to a local PCS (e.g., EPSG:32748 for West Java) first.
4. **Validation**: Always verify layer validity (`layer.isValid()`) and check the `crs().authid()` after geoprocessing to ensure transformations succeed.

## 3. PyQGIS Execution Strategy
Use the `qgis_execute_code` tool to run PyQGIS scripts.
- **Import Statements**: Always import what you need per execution (e.g., `import processing`, `from qgis.core import QgsVectorLayer, QgsProject`). The namespace resets between calls, but the QGIS state persists.
- **Processing Toolbox**: Prefer using `processing.run("native:...")` for standard geoprocessing tasks (like `native:buffer`, `native:reprojectlayer`, `native:fieldcalculator`, `native:extractbylocation`).
- **Memory vs Disk**: When running chained processing algorithms, use `'TEMPORARY_OUTPUT'` for intermediate steps. For final deliverables, save directly to disk (e.g., using `native:savefeatures`) so the user has the final `.shp` files.
- **Canvas Updates**: Always finish your script by explicitly adding the finalized output layers to the QGIS canvas so the user can see your work: `QgsProject.instance().addMapLayer(final_layer)`.

## 4. UI Context and Basemaps
If the user complains about a "blank white screen" despite layers loading, they lack geographical context. Use `qgis_execute_code` to append an OpenStreetMap basemap to the very bottom of their layer tree and zoom to the active layers:
```python
from qgis.core import QgsRasterLayer, QgsProject
uri = "type=xyz&url=https://tile.openstreetmap.org/{z}/{x}/{y}.png&zmax=19&zmin=0"
basemap = QgsRasterLayer(uri, "OpenStreetMap", "wms")
if basemap.isValid():
    QgsProject.instance().addMapLayer(basemap, False)
    QgsProject.instance().layerTreeRoot().insertLayer(-1, basemap)
    # Use iface to zoom to the active layer...
```

## 5. Communication Workflow
1. Provide the user with a detailed execution plan.
2. Ask confirming questions about their specific target CRS and buffer distances.
3. Explicitly ask for permission before running large PyQGIS scripts.
4. Provide a highly detailed summary of the extracted geometry counts and output files upon completion.

</instructions>
</esper_module>
