# Spatiotemporal Signal Propagation Analysis

This project analyzes the spatiotemporal propagation of ERK signals in MCF10A cells, focusing on how different oncogenic mutations in the PI3K-AKT pathway influence cell-to-cell communication.

The main goals of the analysis were:
- To compare the impact of various mutations (e.g., PIK3CA H1047R, AKT1 E17K) on the coordination of ERK signals between neighboring cells.
- To investigate how these mutations affect the speed and dynamics of signal propagation over time.
- To perform a parameter sensitivity analysis to ensure the robustness of the findings.
- To conduct an independent study on how mutations alter the oscillatory patterns of ERK activity.

The project is divided into several tasks, with corresponding Jupyter notebooks in the `notebooks/` directory that cover data processing, analysis, and visualization.

# Generated Data

The `outputs/` directory contains data files generated during the analysis, which are used to create the figures in the report:

*   `jumps.parquet`: Table with all jumps that happend across all sites. Used for jump intervals analysis.
*   `jump_oscilation_violin.png`: Violin plot of distribution of **IJI** for all cell variants.
*   `mutations_barplot.png`: Barplot with average **RR** across selected mutations.
*   `iji_&_neigbours_correlation.csv`: Data correlating inter-jump intervals with the activity of neighboring cells.
*   `intervals_table.csv`: Data on the distribution of inter-jump intervals for different mutations.
*   `lagged_exposure_table.csv`: Relative risk (RR) values calculated for different time delays.
*   `mutations_comparison_table.csv`: Mean relative risk (RR) of ERK signal propagation for each mutation.
*   `ERK_jumps.png`: Raster plot showing jumps of few selected tracks.

# Running the code
## Data
You have to download data using following links and put them in `data/` directory before running the notebooks.
- `data/01-readme-experiment-description_2022-04-05.csv`
- `data/single-cell-tracks_exp1-6_noErbB2.csv.gz` - https://drive.usercontent.google.com/download?id=1nViMkO1WqJOEF9rvkOtfwyab3-YtCWVu&authuser=0
## Initialize virtual environment. 
We used python `3.12.13`.
Core dependencies are: `numpy`, `scipy`, `matplotlib`, `seaborn`, `fastparquet` and `ipykernel`.
In order to create virtual environment you can just run in the reposotory root directory:
```
uv sync
```
The environment should now be ready.
You can now select kernel `spatiotemporal-signal-propagation (Python 3.12.13) .venv/bin/Python` in your python notebook editor of choice and run our code.

To reproduce our findings one can simpy run the notebooks from `notebooks/` directory`. 
It is important to run `notebooks/TaskB2_jump_dataframe_generation.ipynb` **before** `notebooks/TaskB2_downstream_analysis.ipynb`. 