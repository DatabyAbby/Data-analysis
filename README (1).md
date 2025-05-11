# Data Analysis Tool

A standalone data analysis tool that provides comprehensive data processing, visualization, and machine learning capabilities without requiring external APIs.

## Features

- **Data Loading**: Load data from CSV or Excel files
- **Data Cleaning**: 
  - Remove duplicate records
  - Handle missing values (fill with appropriate values or drop rows/columns)
  - Standardize column names
- **Exploratory Data Analysis (EDA)**:
  - Descriptive statistics (mean, median, mode, standard deviation, etc.)
  - Correlation analysis
  - Distribution analysis
  - Outlier detection
- **Data Visualization**:
  - Histograms for distribution analysis
  - Box plots for outlier detection
  - Scatter plots for relationship visualization
  - Correlation heatmaps
  - Bar charts for categorical data
- **Machine Learning Models**:
  - Linear regression
  - Random forest (regression and classification)
  - K-means clustering
- **Summarization**:
  - Generate data quality scores
  - Extract key insights from the analysis
  - Summarize model performance

## How to Use

The tool can be imported as a Python module:

```python
from data_analysis_tool import DataAnalysisTool

# Create a tool instance
tool = DataAnalysisTool()

# Load data (from file content as bytes)
with open('your_data.csv', 'rb') as f:
    file_content = f.read()
success, message = tool.load_data(file_content, file_type='csv')

# Clean data
cleaning_info = tool.clean_data(remove_duplicates=True, handle_missing='fill')

# Perform EDA
eda_results = tool.perform_eda()

# Generate visualizations
viz_data = tool.generate_visualizations()
# Each visualization is returned as a base64-encoded string that can be displayed in various environments

# Build a predictive model
# For regression/classification:
model_results = tool.build_model(target_column='your_target', model_type='random_forest')

# For clustering:
clustering_results = tool.build_model(model_type='kmeans')

# Get a summary of all analysis
summary = tool.get_data_summary()

# Export processed data
csv_data = tool.export_processed_data(format='csv')
```

## Example Client

An example client script (`example_client.py`) is provided to demonstrate the tool's functionality:

```
python example_client.py
```

This will:
1. Create a sample dataset if one doesn't exist
2. Load the dataset into the tool
3. Perform data cleaning
4. Run exploratory data analysis
5. Generate visualizations
6. Build predictive models
7. Summarize the findings

## Integration

This tool can be integrated into:

1. Web applications (using Flask, Django, or Streamlit)
2. Jupyter notebooks for interactive analysis
3. Data processing pipelines
4. Desktop applications

## Requirements

- Python 3.6+
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

## Limitations

- The tool processes data in-memory, so very large datasets may cause performance issues
- Visualizations are returned as base64-encoded strings, not interactive elements
- Advanced ML models (deep learning, etc.) are not included to keep the tool lightweight

## License

MIT