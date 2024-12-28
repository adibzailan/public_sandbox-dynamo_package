# Grid Extent Switcher
> Last Updated: 28 December 2024
> Version: 1.1.3
> Category: Documentation Management

## Overview
Automates switching grid extents between 2D (ViewSpecific) and 3D (Model) modes across multiple views, providing granular control over grid visibility and documentation.

## Purpose
The Grid Extent Switcher node is designed to streamline the process of managing grid visibility across multiple views in Revit. It allows for batch processing of grid extents, enabling quick transitions between 2D (ViewSpecific) and 3D (Model) modes while maintaining precise control over documentation standards.

## Inputs
| Parameter | Type | Required | Description | Default |
|-----------|------|----------|-------------|---------|
| `Views` | List<View> | Yes | List of views to process grids in | - |
| `Make2D` | bool | Yes | Toggle between 2D (true) and 3D (false) modes | - |
| `LogPath` | string | No | Path for error logging | System temp directory |

## Outputs
| Parameter | Type | Description |
|-----------|------|-------------|
| `success_list` | List<ElementId> | List of successfully processed grid IDs |
| `failed_list` | List<ElementId> | List of failed grid IDs |
| `preview` | string | Status messages for Dynamo UI |
| `debug_info` | List<string> | Detailed debug messages |

## Usage Notes
- Views must be valid for printing and not view templates
- Supports batch processing of multiple views simultaneously
- Automatically handles error recovery and logging
- Provides detailed feedback for troubleshooting

## Example Usage
```python
# Example Dynamo workflow
1. Select multiple views using Dynamo nodes
2. Connect views to the Views input
3. Set Make2D to True for ViewSpecific mode or False for Model mode
4. Optionally specify a log file path
5. Run to process all grids in the selected views
```

## Error Handling
- Invalid views are automatically filtered out
- Failed grid operations are logged with detailed error messages
- Transaction rollback on failure to maintain model integrity

## Performance Considerations
- Optimized for batch processing of multiple views
- Efficient grid collection using FilteredElementCollector
- Minimal transaction usage for better performance

## Limitations
- Only processes views that are valid for printing
- Cannot process view templates
- Requires appropriate Revit permissions

## Version History
### v1.1.3 (Current)
- Initial release
- Enhanced logging system with better file access handling
- Improved error recovery
- Standardized namespace organization

## Related Nodes
- None currently

## Additional Resources
- [Public Sandbox Documentation](https://publicsandbox.net)
- Contact: hello@publicsandbox.net 