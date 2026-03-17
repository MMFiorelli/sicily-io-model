# Regional Input-Output (IO) Table Calculator

This repository contains a Python-based pipeline for processing large-scale Regional Input-Output tables. It parses the raw data to calculate essential economic matrices, specifically the Technical Coefficients (A matrix) and the fully resolved Leontief Inverse matrix (L matrix), saving them as lightweight, easily accessible CSV files.

## Data Download Instructions (Important!)

Because the raw regional IO tables amount to approximately 1.6 GB, they are too large to be hosted directly on GitHub. 

To run this code locally, you must download the raw data and place it in the correct folder:

1. **Download the Data:** Download the zipped raw data tables from the [PBL Euregio Data Portal](https://dataportaal.pbl.nl/PBL_Euregio/).
2. **Extract:** Extract the contents of the `.zip` file directly into the `data/raw/` folder of this repository. 
3. **Documentation:** For detailed methodological documentation regarding this dataset, please refer to the [JRC Data Catalogue](https://data.jrc.ec.europa.eu/dataset/84356c3b-104d-4860-8ce3-075d2eab37ab).

*Note: The `data/raw/` folder in this repository contains a `.gitkeep` file to preserve the folder structure. Do not delete this file.*

## 🚀 How to Run the Code

Once your raw data is securely placed in the `data/raw/` folder, you are ready to generate the matrices.

### For Python / Jupyter Users
1. Ensure you have the required packages installed by running:
   `pip install -r requirements.txt`
2. Open `code_v1.ipynb` in Jupyter Notebook or JupyterLab.
3. Run the cells sequentially. The script will automatically read the raw `.xlsb` files and export the finalized Leontief and Technical Coefficient matrices to the `data/processed/` folder.

### For RStudio Users
This pipeline is fully compatible with RStudio via the `reticulate` package.
1. Open your RStudio console and ensure your Python environment has the necessary packages installed based on the `requirements.txt` file.
2. Open the notebook file in RStudio and execute the chunks natively.

## 📦 Requirements

This project requires Python 3.x. All necessary dependencies are listed in the `requirements.txt` file, which includes:
* `pandas`
* `numpy`
* `scipy`
* `pyxlsb` (Required for parsing binary Excel files)
* `matplotlib`
* `openpyxl`
* `pandasgui`

The repository also contains a "convert to Rmarkdown" file. It is python file that, when run, can transform the current 'code_v1.csv' file into a Rmarkdown file (.Rmd). Therefore, whenever alterations are made in the main python file, the programmer shall also run this programm in order to save the same alterations in the Rmarkdown file.