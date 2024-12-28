# Public Sandbox - Dynamo Package
> Updated: 28 December 2024
> Version: 1.1.1

Public Sandbox's active package is designed to augment, automate, and enhance Revit tasks, focusing on documentation and, in the near future, geometry creation. All nodes are performance-optimized C# ZeroTouch implementations, ensuring maximum efficiency and reliability. TLDR: streamline workflows so we can all head home earlier.

## Installation

### Requirements
- Revit 2022+
- Dynamo 2.19+

### Instructions
1. Open Dynamo within Revit
2. Navigate to the **Packages** menu and select **Search for a Package...**
3. Search for `PublicSandbox`
4. Click **Install** to add the package to your Dynamo environment

## Recent Updates (v1.1.0)
- All nodes now use standardized C# ZeroTouch implementation
- Performance optimization across all nodes
- Enhanced error handling and logging
- Improved transaction management
- Standardized namespace to "Geometry" for better categorization

## 3 Recent Nodes

### wall_consolidator
Performance-optimized ZeroTouch node that consolidates wall elements from one level to another while preserving their relative positions, constraints, and relationships.

**Inputs:**
- `SourceLevel`: Level to move walls from
- `TargetLevel`: Level to move walls to
- `LogPath` (optional): Path for error logging

**Outputs:**
- `success_list`: List of successfully processed walls
- `failed_list`: List of walls that failed with error messages
- `success_ids`: ElementIds of successful walls
- `failed_ids`: ElementIds of failed walls

*Note: Ensure elements have valid properties and relationships before processing*

### rooms_to_floors
Performance-optimized ZeroTouch node that creates floor elements from room boundaries with automatic boundary detection and height control.

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

*Note: Ensure rooms have valid boundaries before processing*

### rooms_to_ceilings
Performance-optimized ZeroTouch node that creates ceiling elements from room boundaries with configurable height offset.

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

For inquiries, feedback, or support, please contact me at: hello@publicsandbox.net
Visit my digital space where I document cross-domain works at: [Public Sandbox](https://publicsandbox.net)
