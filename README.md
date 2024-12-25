# Public Sandbox - Dynamo Package

Public Sandbox's active package is designed to augment, automate, and enhance Revit tasks, focusing on documentation and, in the near future, geometry creation. TLDR: streamline workflows so we can all head home earlier.

## Installation

### Requirements
- Revit 2022+
- Dynamo 2.19+

### Instructions
1. Open Dynamo within Revit
2. Navigate to the **Packages** menu and select **Search for a Package...**
3. Search for `PublicSandbox`
4. Click **Install** to add the package to your Dynamo environment

## Nodes
> as per v1.0.0, 25 December 2024

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

*Note: Ensure rooms have valid boundaries before processing*

## Contact

For inquiries, feedback, or support, please contact me at:
hello@publicsandbox.net

Visit my digital space at:
[PublicSandbox](https://publicsandbox.net)
