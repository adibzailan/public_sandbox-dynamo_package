# Public Sandbox - Dynamo Package
> Updated: 1 January 2025
> Version: 1.1.5

Public Sandbox's active package is designed to augment, automate, and enhance Revit tasks, focusing on documentation and, in the near future, geometry creation. All nodes are performance-optimized ZeroTouch implementations, ensuring maximum efficiency and reliability. TLDR: streamline workflows so we can all head home earlier.

## Installation

### Requirements
- Revit 2022+
- Dynamo 2.19+

### Instructions
1. Open Dynamo within Revit
2. Navigate to the **Packages** menu and select **Search for a Package...**
3. Search for `PublicSandbox`
4. Click **Install** to add the package to your Dynamo environment

## Recent Updates (v1.1.5)
- Removed file-based logging in favor of in-memory debugging for significantly improved performance
- Enhanced error handling with comprehensive in-memory debug information
- Standardized namespace organization for better categorization
- Added `floor_consolidator` node for managing floor elements between levels

## 3 Recent Nodes

### floor_consolidator
Consolidates floor elements from one level to another while preserving their relative positions and relationships, with automatic handling of height offsets and level parameters.

**Inputs:**
- `SourceLevel`: Level containing floors to move
- `TargetLevel`: Level to move floors to

**Outputs:**
- `moved_floors`: List of successfully moved floor ElementIds
- `failed_floors`: List of failed floor ElementIds
- `preview`: Status messages and operation summary
- `debug_info`: Detailed debug messages with timestamps

*Note: Requires Revit 2022+ and preserves floor relationships during transfer*

### grid_extent_switcher
Automates switching grid extents between 2D (ViewSpecific) and 3D (Model) modes across multiple views, providing granular control over grid visibility and documentation.

**Inputs:**
- `Views`: List of views to process grids in
- `Make2D`: Boolean to toggle between 2D (true) and 3D (false) modes

**Outputs:**
- `success_list`: List of successfully processed grid IDs
- `failed_list`: List of failed grid IDs
- `preview`: Status messages for Dynamo UI
- `debug_info`: Detailed debug messages

*Note: Views must be valid for printing and not view templates*

### wall_consolidator
Consolidates wall elements from one level to another while preserving their relative positions, constraints, and relationships.

**Inputs:**
- `SourceLevel`: Level to move walls from
- `TargetLevel`: Level to move walls to

**Outputs:**
- `success_list`: List of successfully processed walls
- `failed_list`: List of walls that failed with error messages
- `success_ids`: ElementIds of successful walls
- `failed_ids`: ElementIds of failed walls

*Note: Ensure elements have valid properties and relationships before processing*

## Contact

For inquiries, feedback, or support, please contact me at: hello@publicsandbox.net
Visit my digital space where I document cross-domain works at: [Public Sandbox](https://publicsandbox.net)
