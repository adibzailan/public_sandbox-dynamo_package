# Wall Consolidator
> Last Updated: 29 December 2024
> Version: 1.1.4
> Category: Element Level Management

## Overview
Consolidates wall elements from one level to another while preserving their relative positions, constraints, and relationships.

## Purpose
The Wall Consolidator node is designed to streamline the process of reorganizing wall elements between different levels in Revit. It maintains the integrity of wall relationships and constraints during the transfer, ensuring accurate documentation and model consistency.

## Inputs
| Parameter | Type | Required | Description | Default |
|-----------|------|----------|-------------|---------|
| `SourceLevel` | Level | Yes | Level to move walls from | - |
| `TargetLevel` | Level | Yes | Level to move walls to | - |

## Outputs
| Parameter | Type | Description |
|-----------|------|-------------|
| `success_list` | List<Wall> | List of successfully processed walls |
| `failed_list` | List<string> | List of walls that failed with error messages |
| `success_ids` | List<ElementId> | ElementIds of successful walls |
| `failed_ids` | List<ElementId> | ElementIds of failed walls |

## Usage Notes
- Ensure elements have valid properties and relationships before processing
- Validates wall constraints and relationships before transfer
- Maintains wall joins and connections during consolidation
- Provides detailed feedback for failed operations

## Example Usage
```python
# Example Dynamo workflow
1. Select source level using Level.ByName or similar
2. Select target level using Level.ByName or similar
3. Connect levels to respective inputs
4. Optionally specify a log file path
5. Run to consolidate walls between levels
```

## Error Handling
- Validates wall geometry before processing
- Maintains transaction integrity with rollback on failure
- Detailed logging of failed operations with reasons
- Preserves original walls if operation fails

## Performance Considerations
- Optimized for batch processing of multiple walls
- Efficient element collection using FilteredElementCollector
- Smart transaction management for better performance
- Minimal memory footprint during processing

## Limitations
- Only processes walls with valid geometry
- Cannot transfer hosted elements automatically
- Requires appropriate Revit permissions
- Some complex wall joins may need manual verification

## Version History
### v1.1.4 (Current)
- Removed file-based logging in favor of in-memory debugging for significantly improved performance
- Enhanced error handling with comprehensive in-memory debug information
- Standardized namespace organization for better categorization

### v1.1.3
- Enhanced logging system with better file access handling
- Improved error recovery
- Standardized namespace organization

### v1.0.1
- Initial release
- Basic wall consolidation functionality
- Error handling and logging implementation

## Related Nodes
- None currently

## Additional Resources
- [Public Sandbox Documentation](https://publicsandbox.net)
- Contact: hello@publicsandbox.net 