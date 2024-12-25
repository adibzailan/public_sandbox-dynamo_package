# Public Sandbox - Node Catalog
> Last updated: 25 December 2024

This document tracks all nodes available in the Public Sandbox Dynamo Package, organized by version.

## Current Version (v1.0.1)

### Element Level Management
| Node Name | Description | Added In | Status |
|-----------|-------------|----------|---------|
| `wall_consolidator` | Consolidates wall elements between levels while preserving relationships | v1.0.1 | Active |

### Rooms to Elements Processing
| Node Name | Description | Added In | Status |
|-----------|-------------|----------|---------|
| `rooms_to_floors` | Creates floor elements from room boundaries with automatic boundary detection and height control | v1.0.0 | Active |
| `rooms_to_ceilings` | Creates ceiling elements from room boundaries with configurable height offset | v1.0.0 | Active |

## Version History

### v1.0.1 (25 December 2024)
- Added `wall_consolidator` node
- Added `rooms_to_floors` node
- Added `rooms_to_ceilings` node
- Initial release

## Node Details

### wall_consolidator
Consolidates wall elements from one level to another while preserving their relative positions, constraints, and relationships.

**Inputs:**
- `SourceLevel`: Level to move walls from
- `TargetLevel`: Level to move walls to
- `LogPath` (optional): Path for error logging

**Outputs:**
- `success_list`: List of successfully processed walls
- `failed_list`: List of walls that failed with error messages
- `success_ids`: ElementIds of successful walls
- `failed_ids`: ElementIds of failed walls

### rooms_to_floors
Creates floor elements from room boundaries with automatic boundary detection and height control.

**Inputs:**
- `Rooms`: List of rooms to process
- `FloorType`: Floor type for creation
- `Level`: Level for floor placement
- `LogPath` (optional): Path for error logging
- `Offset` (optional): Height offset in millimeters (default: 0)

**Outputs:**
- `created_floors`: List of created floor ElementIds
- `failed_rooms`: List of rooms that failed processing
- `debug_info`: List of critical messages
- `preview`: Status messages for Dynamo UI

### rooms_to_ceilings
Creates ceiling elements from room boundaries with configurable height offset.

**Inputs:**
- `Rooms`: List of rooms to process
- `CeilingType`: Ceiling type for creation
- `Level`: Level for ceiling placement
- `LogPath` (optional): Path for error logging
- `Offset` (optional): Height offset in millimeters (default: 2700)

**Outputs:**
- `created_ceilings`: List of created ceiling ElementIds
- `failed_rooms`: List of rooms that failed processing
- `debug_info`: List of critical messages
- `preview`: Status messages for Dynamo UI

*Note: This catalog is maintained separately from the package README to provide historical tracking and detailed documentation of all nodes.* 