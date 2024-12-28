# Public Sandbox - Dynamo Package
> Updated: 28 December 2024
> Version: 1.1.3

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

## Recent Updates (v1.1.3)
- Added new `grid_extent_switcher` node for automated grid extent management
- Enhanced logging system with better file access handling
- Improved error recovery across all nodes
- Standardized namespace organization for better categorization

## 3 Recent Nodes

### grid_extent_switcher
Performance-optimized ZeroTouch node that automates switching grid extents between 2D (ViewSpecific) and 3D (Model) modes across multiple views, providing granular control over grid visibility and documentation.

**Inputs:**
- `Views`: List of views to process grids in
- `Make2D`: Boolean to toggle between 2D (true) and 3D (false) modes
- `LogPath` (optional): Path for error logging

**Outputs:**
- `success_list`: List of successfully processed grid IDs
- `failed_list`: List of failed grid IDs
- `preview`: Status messages for Dynamo UI
- `debug_info`: Detailed debug messages

*Note: Views must be valid for printing and not view templates*

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

## Contact

For inquiries, feedback, or support, please contact me at: hello@publicsandbox.net
Visit my digital space where I document cross-domain works at: [Public Sandbox](https://publicsandbox.net)
