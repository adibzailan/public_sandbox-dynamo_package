# Floor Consolidator
> Last Updated: 1 January 2025
> Version: 1.0.0
> Category: Category: Element Level Management

## Overview
Consolidates floor elements from one level to another while preserving their relative positions and relationships, handling height offsets and level parameters automatically.

## Purpose
The Floor Consolidator node streamlines the process of reorganizing floor elements between different levels in Revit. It maintains the integrity of floor relationships, height offsets, and level-based parameters during the transfer, ensuring accurate documentation and model consistency.

## Inputs
| Parameter | Type | Required | Description | Default |
|-----------|------|----------|-------------|---------|
| `sourceLevel` | Level | Yes | Level containing floors to move | - |
| `targetLevel` | Level | Yes | Level to move floors to | - |

## Outputs
| Parameter | Type | Description |
|-----------|------|-------------|
| `moved_floors` | List<ElementId> | List of successfully moved floor ElementIds |
| `failed_floors` | List<ElementId> | List of failed floor ElementIds |
| `preview` | string | Status messages and operation summary |
| `debug_info` | List<string> | Detailed debug messages with timestamps |

## Usage Notes
- Ensures floor elements have valid properties before processing
- Maintains floor height offsets relative to new level
- Validates floor constraints and relationships before transfer
- Provides detailed feedback and logging for all operations

## Example Usage
```python
# Example Dynamo workflow
1. Select source level using Level.ByName node
2. Select target level using Level.ByName node
3. Connect levels to Floor Consolidator node
4. Review outputs for success/failure status
5. Check debug_info for detailed operation logs
```

## Error Handling
- Validates floor geometry before processing
- Maintains transaction integrity with rollback on failure
- Detailed timestamped logging of all operations
- Preserves original floors if operation fails
- Error messages include affected element IDs for tracing

## Performance Considerations
- Optimized for batch processing of multiple floors
- Efficient element filtering and collection
- Smart transaction management
- Minimal memory footprint with streaming operations

## Limitations
- Requires Revit 2022 or later
- Requires Dynamo 2.19 or later
- May not preserve certain complex floor system families
- Custom floor types should be present in target document
