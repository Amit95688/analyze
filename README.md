# Data Processing and CI/CD Example

This repository demonstrates a robust data processing pipeline using Python, Pandas, Ruff for linting, and GitHub Actions for continuous integration and deployment to GitHub Pages.

## Project Overview

The core of this project is a Python script (`execute.py`) that reads and processes data from a CSV file (`data.csv`). The processing involves summing numerical values grouped by categories, designed to be resilient to common data quality issues.

### Key Features:
- **Data Processing:** A Python script (`execute.py`) that performs aggregation on tabular data.
- **Error Handling:** The script is designed to gracefully handle non-numeric data, ensuring robust execution.
- **Code Quality:** Integrated `ruff` linter to maintain high code quality standards.
- **Automated Workflow:** GitHub Actions automates the linting, data processing, and deployment steps.
- **GitHub Pages Deployment:** The processed output (`result.json`) is automatically published to GitHub Pages, making the results easily accessible.

## Files in this Repository

- `index.html`: A simple, responsive landing page providing an overview and a link to the processed data.
- `execute.py`: The Python script responsible for data processing. It reads `data.csv`, groups data by 'Category', and sums 'Value's, handling non-numeric entries by coercing them.
- `data.xlsx`: The original Excel data file provided.
- `data.csv`: A CSV version of `data.xlsx`, committed to the repository. The `execute.py` script uses this file as its input.
- `LICENSE`: The MIT License text.
- `.github/workflows/ci.yml`: GitHub Actions workflow definition for linting, execution, and deployment.

## Data Structure

The `data.xlsx` (and subsequently `data.csv`) is expected to have at least two columns: `Category` and `Value`.

Example `data.csv` content:
```csv
Category,Value
A,100
B,200
A,50
C,150
B,N/A
A,75
D,invalid_value
```

## Getting Started

Follow these instructions to set up and run the project locally.

### Prerequisites

- Python 3.11+
- pip (Python package installer)

### Local Setup

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/your-repo-name.git
    cd your-repo-name
    ```
    (Replace `your-username/your-repo-name` with your actual repository path.)

2.  **Install dependencies:**
    ```bash
    pip install pandas ruff
    ```

3.  **Run the linter (optional, but recommended):**
    ```bash
    ruff check .
    ```

4.  **Execute the data processing script:**
    ```bash
    python execute.py > result.json
    ```
    This will generate `result.json` in your local directory.

## Continuous Integration and Deployment (CI/CD)

The project uses GitHub Actions to automate the workflow. The `.github/workflows/ci.yml` file defines the following steps:

1.  **Checkout repository:** Fetches the code.
2.  **Setup Python 3.11:** Configures the Python environment.
3.  **Install dependencies:** Installs `pandas` and `ruff`.
4.  **Run Ruff Linter:** Checks Python code for style and errors.
5.  **Generate `result.json`:** Executes `execute.py` and redirects its output to `result.json`.
6.  **Deploy to GitHub Pages:** Publishes `result.json` (and `index.html` if configured in Pages settings) to GitHub Pages.

### Accessing Results

After a successful push to the `main` branch, the `result.json` file will be published to GitHub Pages. You can typically find it at:

`https://<your-username>.github.io/<your-repository-name>/result.json`

The `index.html` file will also be served, providing a direct link.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.