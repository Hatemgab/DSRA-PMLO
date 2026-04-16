# DSAR-PMLO
**A parametric adaptive sampling algorithm for efficient IoT data collection.**

## Result Demonstration
<div align="center">
  <video src="./assets/result_animation.mp4" width="80%" controls muted>
  </video>
</div>
> *Above: Dynamic demonstration of the adaptive sampling process。*


## Project Overview
This tool focuses on the analysis and reconstruction of wireless sensor data. In the context of IoT, data transmission is the most energy-consuming activity in Wireless Sensor Networks(WSNs). The goal of this project is to transmit data efficiently by collecting the minimum amount of samples required to meet a predetermined error threshold.

## Environment Setup
1. **Clone the repository:**
```bash
# Using HTTPS (Recommended for most users)
git clone https://github.com/Hatemgab/DSAR-PMLO.git
cd DSAR-PMLO
```
2. Install dependencies:
```bash
python3 -m pip install -r requirements.txt
```
3. Verify environment:
Run the following script to check your Python path and library availability:
```bash
python3 path.py
```

## Video Demonstration
[![Video Demo](https://img.shields.io/badge/Video-Demo-red)](video_address)
> *Click the badge above to watch a short video on how to use the Manual and Automated modes.*

## Which Program Should I Use?
| Feature | **Manual Mode** (`DSRA-BPML...`) | **Automated Mode** (`DSRA-PMLO...`) |
| :--- | :--- | :--- |
| **Speed** | **Fast** (~2-5 mins) | **Slower** (~15-30 mins*) |
| **Effort** | User-guided tuning required | Fully autonomous |
| **Visualization**| 3-Step Heatmap 'Zoom' | Result summary only |

*\*Note: Automated runtime depends on the dataset size and hardware.*

## Step-by-Step Instructions
1. Data Setup
Save your data in the /data folder. The file must be in .txt or .csv format.

2. Running Your Chosen Mode
Option A: Automated Mode (Set and Forget)
Use this if you want the program to handle the optimization of E and S parameters automatically.
1. Open DSRA-PMLO_automated_corrected.ipynb.
2. Parameters Configuration(usually Cell 2): Define your column name, SIMILARITY_METHOD (MAAPE recommended), and SIMILIARITY_THRESHOLD(e.g., 2 for 2% error).
3. File Path(usually Cell 3): Update the filename to match yoru dataset in the /data folder.
4. Parameter Mapping(usually Cell 4): Update the attribute name (e.g., change .Amplitude to your specific heading).
5. Execute: Click "Run All" to find the optional parameters.

Option B: Manual Mode (Interactice Tuning)
1. Open DSRA-BPML paper-2% quadratic.ipynb.
2. Setup (Cells 22-23): Follow the same parameter setup as Automated Mode.
3. Column Mapping (Cell 24): Crucial!In the first and the third rows, replace 'temp' and 'humi' with the exact column names from your data file.
4. The 3-Step 'Zoom' (Cells 32-34): 
   - Step 1 : Run a broad scan using plot2d to identify the general trend.
   - Step 2 : Locate the dark purple region (lowest error) and the narrow range in the next cell to focus on that area. 
   - Step 3 : Perform a final high-resolution scan to lock down the optimal E(Explore) and S(Sensitivity) values.
#### **Manual Mode Optimization Example:**
| Step 1: Broad | Step 2: Narrow | Step 3: Final |
| :---: | :---: | :---: |
| ![Step 1](./assets/heatmap_step1.png) | ![Step 2](./assets/heatmap_step2.png) | ![Step 3](./assets/heatmap_step3.png) |

## Questions & Feedback
Please open a GitHub Issue. This allows the community to benefit from the discussion and ensures the project remains maintainable.
