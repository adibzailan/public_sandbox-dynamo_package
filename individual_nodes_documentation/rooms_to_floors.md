# Rooms to Floors
> Last Updated: 28 December 2024
> Version: 1.1.3
> Category: Rooms to Elements Processing

## Overview
Creates floor elements from room boundaries with automatic boundary detection and height control.

## Purpose
The Rooms to Floors node automates the creation of floor elements based on room boundaries in Revit. It streamlines the process of generating accurate floor geometry while providing control over height offsets and maintaining model integrity.

## Inputs
| Parameter | Type | Required | Description | Default |
|-----------|------|----------|-------------|---------|
| `Rooms` | List<Room> | Yes | List of rooms to process | - |
| `FloorType` | FloorType | Yes | Floor type for creation | - |
| `Level` | Level | Yes | Level for floor placement | - |
| `LogPath` | string | No | Path for error logging | System temp directory |
| `Offset` | double | No | Height offset in millimeters | 0 |

## Outputs
| Parameter | Type | Description |
|-----------|------|-------------|
| `created_floors` | List<ElementId> | List of created floor ElementIds |
| `failed_rooms` | List<Room> | List of rooms that failed processing |
| `debug_info` | List<string> | List of critical messages |
| `preview` | string | Status messages for Dynamo UI |

## Usage Notes
- Ensure rooms have valid boundaries before processing
- Validates room geometry before floor creation
- Supports batch processing of multiple rooms
- Provides detailed feedback for failed operations

## Example Usage
```python
# Example Dynamo workflow
1. Select rooms using Room.ByName or similar
2. Select floor type using FloorType.ByName
3. Select level using Level.ByName
4. Optionally set height offset (default: 0mm)
5. Optionally specify a log file path
6. Run to create floors from room boundaries
```

## Error Handling
- Validates room boundaries before processing
- Maintains transaction integrity with rollback on failure
- Detailed logging of failed operations with reasons
- Skips invalid rooms while continuing processing

## Performance Considerations
- Optimized for batch processing of multiple rooms
- Efficient boundary extraction using Revit API
- Smart transaction management for better performance
- Minimal memory footprint during processing

## Limitations
- Only processes rooms with valid boundaries
- Cannot handle overlapping room boundaries
- Requires appropriate Revit permissions
- Some complex room geometries may need manual verification

## Version History
### v1.1.3 (Current)
- Enhanced logging system
- Improved error recovery
- Standardized namespace organization

### v1.0.0
- Initial release
- Basic room to floor conversion
- Error handling and logging implementation

## Related Nodes
- `rooms_to_ceilings`: Creates ceiling elements from room boundaries

## Additional Resources
- [Public Sandbox Documentation](https://publicsandbox.net)
- Contact: hello@publicsandbox.net 