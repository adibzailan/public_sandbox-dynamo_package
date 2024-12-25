# Public Sandbox - Node Catalog
> Last updated: 25 December 2024

This document tracks all nodes available in the Public Sandbox Dynamo Package, organized by version.

## Current Version (v1.0.0)

### Room Processing
| Node Name | Description | Added In | Status |
|-----------|-------------|----------|---------|
| `rooms_to_floors` | Creates floor elements from room boundaries with automatic boundary detection and height control | v1.0.0 | Active |
| `rooms_to_ceilings` | Creates ceiling elements from room boundaries with configurable height offset | v1.0.0 | Active |

## Version History

### v1.0.0 (25 December 2024)
- Initial release
- Added `rooms_to_floors` node
- Added `rooms_to_ceilings` node

## Node Details

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

## Future Plans
- Geometry creation tools (planned)
- Documentation automation tools (planned)

*Note: This catalog is maintained separately from the package README to provide historical tracking and detailed documentation of all nodes.* 