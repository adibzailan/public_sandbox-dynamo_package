# Public Sandbox - Node Catalog
> Last updated: 1 January 2025

This document tracks all nodes available in the Public Sandbox Dynamo Package, organized by version. All nodes are implemented as performance-optimized ZeroTouch nodes for maximum efficiency and reliability.

## Current Version (v1.1.5)

### Documentation Management
| Node Name | Description | Added In | Status |
|-----------|-------------|----------|---------|
| `grid_extent_switcher` | Automating grid extent switching between 2D/3D modes across multiple views | v1.1.3 | Active |

### Element Level Management
| Node Name | Description | Added In | Status |
|-----------|-------------|----------|---------|
| `wall_consolidator` | Consolidating wall elements between levels while preserving relationships | v1.0.1 | Active |
| `floor_consolidator` | Consolidating floor elements between levels while preserving positions and offsets | v1.1.5 | Active |

### Rooms to Elements Processing
| Node Name | Description | Added In | Status |
|-----------|-------------|----------|---------|
| `rooms_to_floors` | Creating floor elements from room boundaries with automatic boundary detection and height control | v1.0.0 | Active |
| `rooms_to_ceilings` | Creating ceiling elements from room boundaries with configurable height offset | v1.0.0 | Active |

## Version History

### v1.1.5 (1 January 2025)
- Added `floor_consolidator` node

### v1.1.4 (29 December 2024)
- Removed file-based logging in favor of in-memory debugging for significantly improved performance
- Enhanced error handling with comprehensive in-memory debug information
- Standardized namespace organization for better categorization

### v1.1.3 (28 December 2024)
- Added `grid_extent_switcher` node for automated grid extent management
- Enhanced logging system with better file access handling
- Improved error recovery across all nodes
- Standardized namespace organization for better categorization

### v1.1.1 (28 December 2024)
- Standardized all nodes to use ZeroTouch implementation pattern
- Optimized performance for all existing nodes
- Enhanced error handling and logging across all nodes
- Improved transaction management for better reliability
- Standardized namespace to "Geometry" for better categorization and organization

### v1.0.1 (25 December 2024)
- Added `wall_consolidator` node
- Added `rooms_to_floors` node
- Added `rooms_to_ceilings` node
- Initial release

*Note: This catalog is maintained separately from the package README to provide historical tracking and detailed documentation of all nodes. All nodes follow a standardized implementation pattern for optimal performance and maintainability.*