# Comprehensive-evacuation-route-analysis

The comprehensive evacuation route analysis (CEA) is a multi-objective path-finding model that calculates evacuation routes considering both objectives: 1) to reduce evacuation distance and 2) road hazard. Multi-objective path finding is a practical approach to find the best decision between conflicting objectives. Previous research proposed algorithms that optimize costs to calculate a single best solution for all objectives by setting maximum cost of each objective or rank of objectives. Since mobile phone data updates hourly, an efficient multi-objective path-finding algorithm is necessary to calculate evacuation routes rapidly for proactive planning. 

* Step 1: Calculate a group of paths (R) that minimizes road hazards between population nodes and shelter nodes
* Step 2: Identify the shortest path from population node i to shelter node j in R, where P_i > 0 and C_j > 0
* Step 3: If C_j ≥ P_i, assign P_i to the path. Next, C_j = C_j - P_i and P_i = 0
* Step 4: If C_j < P_i, assign P_i - C_j to the path. Next, C_j = 0 and P_i = P_i - C_j
* Step 5: If the sum of populations or shelter capacities is zero, end the process. If not, we iterate at step 2
