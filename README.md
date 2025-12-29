# ps1
 
This repository contains the perception and path-planning stack developed for the Stark Industries PS1 Challenge. The system is designed to navigate a 20X20 grid across three different environments (Lab, Forest, and Desert). 
Project Overview :localized EMP has crippled Stark Industries' autonomous logistics network.
This project does the following :
    Identify Terrain: Categorize maps into Lab, Forest, or Desert themes.
    Classify Tiles: Decode 400 grid cells into classes: Path, Wall, Hazard, Start, or Goal 
    Optimize Pathing: Compute a move sequence (l, r, u, d) that minimizes total cost by leveraging "Velocity Boosts" . 
Technical Methodology. 
    Perception & Classification :Since the underlying class grid is hidden, we use a prototype-based classification approach 
    Feature Extraction: Each tile is represented by the Mean and Standard Deviation of its RGB channels.
    Terrain Recognition: We use K-Means clustering to distinguish between the three environment themes based on global image features.
    Nearest-Neighbor Decoding: Tiles are classified by matching their features to the closest class prototype within the identified terrain type.
    Movement Cost Model The system calculates the cost of every move to ensure energy efficiency7.Base Costs: Each terrain has a unique cost structure for traversal
    Boost Integration: The final cost of moving into a cell (i, j) is :step_cost(i,j) = base_cost(i,j) - boost(i,j).
    Path Planning We utilize Dijkstra’s Algorithm to find the near-optimal sequence of 4-connected steps. 
    The algorithm ignores Class 1 (Walls) and prioritizes the lowest accumulated step_cost to reach the Goal tile.
submission.csv is The final output containing the move sequence (path) . 
How to Run Environment: Ensure you have Python, OpenCV, NumPy, and scikit-learn installed or run in kaggle  .
Execution: Run the script to process test images and generate the submission file
