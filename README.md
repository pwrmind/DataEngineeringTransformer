# Data Engineering Transformer

## Overview

Data Engineering Transformer is a powerful Single Page Application (SPA) designed for data engineers and analysts to interactively transform JSON data through a visual pipeline interface. The application allows users to load, transform, and export data using a chain of transformation steps, with each step creating an immutable copy of the data from the previous step.

## Features

### 🚀 Core Functionality
- **Interactive Data Pipeline**: Create and manage transformation pipelines visually
- **Immutable Data Flow**: Each step works with a deep copy of previous step's data
- **Multiple Data Sources**: Load JSON data from file upload or direct text input
- **Real-time Preview**: See results instantly at each transformation step

### 🔧 Transformation Methods
- **Map**: Element-wise transformation with custom JavaScript expressions
- **Filter**: Filter data based on custom conditions
- **Reduce**: Aggregate data to a single value
- **FlatMap**: Transform and flatten nested arrays
- **Slice**: Extract subsets of arrays
- **Concat**: Merge multiple arrays
- **Join**: Combine array elements into strings

### 🎨 Visualization & UI
- **Pipeline Visualization**: D3.js-powered visual representation of the transformation pipeline
- **Responsive Design**: Bootstrap-based UI with compact layouts
- **Real-time Results**: See immediate results for each transformation step
- **Data Preview**: Table view of data at every pipeline stage

### 📁 Data Management
- **File Upload**: Load JSON data from files
- **Text Input**: Paste JSON data directly
- **Export Options**: Copy to clipboard or download as JSON file
- **Sample Data**: Pre-loaded sample data for quick testing

## Technology Stack

- **Frontend Framework**: Alpine.js for reactive state management
- **UI Framework**: Bootstrap 5 with compact styling (sm classes)
- **Visualization**: D3.js for pipeline visualization
- **Icons**: Font Awesome 6
- **Typography**: Google Fonts (Roboto)
- **Dependencies**: All via CDN - no build process required

## Quick Start

1. **Clone or Download**
   ```bash
   git clone [repository-url]
   ```
   Or simply download the `index.html` file.

2. **Open in Browser**
   Open `index.html` in any modern web browser. No server required!

3. **Start Transforming**
   - Load your JSON data (upload file or paste text)
   - Add transformation steps
   - Configure parameters
   - Export your results

## Usage Guide

### Loading Data
1. **Upload JSON File**: Click "Choose File" to upload a JSON file
2. **Paste JSON**: Directly paste JSON array data into the text area
3. **Use Sample Data**: Click "Reset to Sample" to load example data

### Creating Transformations
1. **Add Steps**: Click "Add Transformation Step" at the bottom of the pipeline
2. **Select Method**: Choose from 7 transformation methods
3. **Configure Parameters**: Set method-specific parameters
4. **Execute**: Click "Apply Transformation" to run the step
5. **View Results**: See immediate results in the step's preview table

### Managing Pipeline
- **Re-order Steps**: Not currently supported (planned feature)
- **Delete Steps**: Click the trash icon on any step
- **Re-execute**: Modify parameters and re-apply transformations
- **Visual Navigation**: Click on pipeline visualization nodes to scroll to specific steps

### Exporting Results
- **Copy to Clipboard**: Click the "Copy" button to copy final data
- **Download JSON**: Click "Export" to download as JSON file

## Data Format

The application expects JSON data in the following format:
```json
[
  { "field1": "value1", "field2": "value2" },
  { "field1": "value3", "field2": "value4" },
  ...
]
```

## Transformation Examples

### Example 1: Filter and Map
```
Source → Filter (age > 25) → Map (extract name and age) → Export
```

### Example 2: Complex Pipeline
```
Source → Filter (active == true) → Map (calculate score) → Reduce (sum scores) → Export
```

## Architecture

### Data Flow
```
Raw Data → [Step 1] → Data Copy 1 → [Step 2] → Data Copy 2 → ... → Final Data
```

### State Management
- **originalData**: Immutable source data
- **pipelineSteps**: Array of transformation configurations
- **currentResults**: Results after each step (immutable copies)
- **Reactive Updates**: Alpine.js manages state and UI updates

## Browser Compatibility

- ✅ Chrome (latest)
- ✅ Firefox (latest)
- ✅ Safari (latest)
- ✅ Edge (latest)

## Security Notes

⚠️ **Important**: The application uses `Function()` constructor to evaluate transformation expressions. This could be a security risk if used with untrusted data. For production use:

1. Implement expression sandboxing
2. Add input validation
3. Consider server-side transformation for sensitive data

## Development

### Project Structure
```
index.html          # Complete application (single file)
```

### No Build Process Required
The application is entirely contained in one HTML file with all dependencies loaded via CDN.

### Customization
- **Styling**: Modify the `<style>` section in the HTML
- **Functionality**: Extend the `app()` function in the `<script>` section
- **New Transformations**: Add new methods to the `executeStep` switch statement

## Limitations

- Maximum data size limited by browser memory
- No undo/redo functionality (planned)
- No collaborative features
- No persistent storage (data lost on page refresh)
- No version control for pipelines

## Future Enhancements

Planned features:
- Undo/Redo functionality
- Pipeline versioning
- Collaboration features
- More transformation methods
- Data type validation
- Performance optimizations for large datasets

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make changes in the single HTML file
4. Test thoroughly
5. Submit a pull request

## License

MIT License - see LICENSE file for details

## Support

For issues and feature requests, please use the GitHub issue tracker.

---

**Note**: This is a frontend-only application. All data processing happens in the browser. No data is sent to external servers unless explicitly exported.
