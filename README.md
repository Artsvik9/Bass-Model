# Bass Model

## Project overview

This project applies the **Bass Diffusion Model** to analyze and compare the adoption of the tri-fold smartphone with traditional smartphones. By estimating key diffusion parameters from historical smartphone data, the model predicts the potential adoption curve of tri-fold smartphones, assessing their market impact and future growth trends.

## Repository Structure

- `Data/` - A folder that contains the dataset for analysis.
- `Report/` - A folder that contains the final report and the markdown source file.
- `Script/` - A folder that contains the Python scripts for data analysis and modeling.
- `Images/` - A folder that contains visualizations generated during analysis.

## Requirements

To run the analysis, install the necessary dependencies:

```sh
import numpy as np
import pandas as pd
import scipy.optimize as opt
import matplotlib.pyplot as plt
```

## Outputs

- Estimated Bass Model parameters (`p`, `q`, `M`).
- Graph showing observed vs. predicted adoption.

## Reason of comparing these 2 innovations

The tri-fold smartphone builds on the innovation of traditional smartphones by enhancing functionality with a foldable design that expands screen size while maintaining portability. Unlike early smartphones, which revolutionized communication and app ecosystems, tri-fold devices push multitasking and media consumption to new levels through advanced flexible displays and hinge technology. While smartphones transformed global markets, the tri-fold remains a niche, premium innovation with potential for wider adoption as costs decrease and durability improves.

## Scope of Analysis

For this analysis, I have chosen the **United States** as the scope for diffusion modeling. The U.S. is one of the largest smartphone markets, with a strong consumer base for premium devices and early adoption of technological innovations. Additionally, leading smartphone manufacturers launch their latest models in the U.S. first, making it an ideal market to analyze adoption trends. By focusing on the U.S., the study can leverage reliable market data, consumer trends, and historical adoption patterns to make accurate diffusion predictions for tri-fold smartphones.# Bass-Model
# Bass-Model
