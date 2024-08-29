# GovTech-Restaurant-Assessment
This project focuses on extracting, processing, and analyzing restaurant data from a JSON dataset, with a particular emphasis on events that took place in April 2019. The output is stored in CSV format, making it accessible for further analysis or integration with other systems.
## 1. Instructions on How to Run the Source Code Locally
### Prerequisites
- **Python 3.x** installed on your system.
- **pip** package manager to install dependencies.
- **Internet access** to download required data files.
### Installation
1. **Clone this Repository:**
```bash
git clone https://github.com/brendanchan03/GovTech-Restaurant-Assessment.git
cd GovTech-Restaurant-Assessment
```
2. **Set Up a Virtual Environment (Recommended):**
```bash
python -m venv venv
source venv/bin/activate # On Windows use: venv\Scripts\activate
```
### Running the Code
**Option 1: Using Jupyter Notebook**
1. Start Jupyter Notebook
2. Open main.ipynb in your browser.
3. Run all cells to execute the data processing steps, which will generate restaurants.csv and restaurant_events.csv in the project directory.
**Option 2: Running as a Python Script**
1. Convert the Jupyter notebook to a Python script:
```bash
jupyter nbconvert --to script main.ipynb
```
2. Execute the script:
```bash
python main.py
```
This will accomplish the same tasks as the notebook, producing the required CSV files.


