# Vehicular-Networks-A-Study-on-Centroid-Localization-and-Error-Analysis
Of course. Here is a comprehensive `README.md` file for your GitHub repository.

-----

# Centroid Localization in Vehicular Networks

This project implements the **Centroid Localization** algorithm, a V2V-based method for estimating vehicle positions in a Vehicular Ad Hoc Network (VANET). The simulation is performed using Python with `pandas` for data manipulation and `matplotlib` for visualization. [cite\_start]The primary goal is to estimate a vehicle's position by averaging the coordinates of its neighbors and then to evaluate the accuracy of this method by calculating the **Average Localization Error**[cite: 1].

This implementation is based on the concepts discussed in the provided lecture notes on vehicle localization.

-----

## Key Concepts

  * **Localization**: The process of determining the real-time position of vehicles, which is critical for most VANET protocols, algorithms, and applications.
  * **Centroid Localization**: A vehicle determines its position by calculating the center point (centroid) of all its neighboring vehicles that are within a specific communication radius.
  * [cite\_start]**Localization Error**: The Euclidean distance between a vehicle's actual, true position and its estimated position (the calculated centroid)[cite: 1]. [cite\_start]This metric is used to evaluate the performance of the localization algorithm[cite: 1].

-----

## Project Structure

```
├── Assignment2_VehicularNetworks.ipynb   # The main Jupyter Notebook with the full implementation.
├── vehicle_data.csv                      # The dataset containing vehicle IDs and their coordinates.
├── Chapter2_Localization.pdf             # Reference slides on localization in VANETs.
├── Chapter3_Weighted Localization in VANETs.pdf # Reference slides on weighted localization methods.
└── README.md                             # You are here.
```

-----

## Methodology

The implementation follows a step-by-step process as detailed in the Jupyter Notebook:

1.  **Load Data**: The `vehicle_data.csv` file, containing the true positions of 15 vehicles, is loaded into a pandas DataFrame.
2.  **Visualization**: The initial true positions of all vehicles are plotted on a 2D graph.
3.  **Neighbor Identification**: A communication **radius of 25 units** is defined. For each vehicle, the script identifies its "neighbors" by calculating the Euclidean distance to every other vehicle and checking if it falls within the radius.
4.  **Centroid Calculation**: For each vehicle, the centroid is calculated by averaging the latitude and longitude of its identified neighbors.
5.  **Error Calculation**: The localization error for each vehicle is computed by finding the Euclidean distance between its true position and its calculated centroid.
6.  **Average Error**: The average localization error is calculated across all vehicles that had at least one neighbor, providing a single metric for algorithm performance.
7.  **Final Visualization**: A final plot is generated to visually compare the true positions with the estimated centroid positions, with dashed lines illustrating the error for each vehicle.

-----

## How to Run

1.  Ensure you have Python installed.
2.  Install the required libraries:
    ```bash
    pip install pandas numpy matplotlib jupyter
    ```
3.  Clone this repository to your local machine.
4.  Launch Jupyter Notebook:
    ```bash
    jupyter notebook
    ```
5.  Open the `Assignment2_VehicularNetworks.ipynb` file and run the cells.

-----

## Results

The script successfully calculates the centroid for each vehicle based on its neighbors and computes an **Average Localization Error of 16.58 units**.

The final output is a visualization that clearly shows the discrepancy between the true and estimated positions, offering insight into the accuracy of the centroid localization method for this specific network topology and communication range.
