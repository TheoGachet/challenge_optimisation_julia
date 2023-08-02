# Surveillance Optimization in Python

This repository contains the Julia code to optimize the placement of surveillance points to cover specific targets while avoiding obstacles in a 2D grid. The goal is to minimize the number of surveillance points needed to effectively monitor all targets in the grid.

**Table of Contents:**

1. Introduction
2. Requirements
3. Usage
4. Input File Format
5. Output
6. Results
7. Contributing
8. License

**1. Introduction:**

The Surveillance Optimization Project aims to find an optimal placement of surveillance points in a 2D grid to monitor specified targets effectively. The project uses the JuMP package in Julia, along with the HiGHS optimizer, to formulate and solve an integer linear programming problem.

**2. Requirements:**

- Julia (version 1.0 or higher)
- JuMP.jl package
- HiGHS.jl package

**3. Usage:**

To use the code, make sure you have Julia installed on your system. Clone this repository and install the required packages:

```
using Pkg
Pkg.add("JuMP")
Pkg.add("HiGHS")
```

Next, place the input file containing the grid configuration and target information in the "Instances" folder. Run the Julia script "surveillance_optimization.jl" to perform the optimization:

```
julia surveillance_optimization.jl
```

The optimized surveillance points will be stored in the "Submissions" folder in a file named "res_16.txt" for instance 16. You can change the input file name and modify the code for different instances.

**4. Input File Format:**

The input file should be a plain text file containing the following information:

- First line: Number of rows (e.g., `10`).
- Second line: Number of columns (e.g., `10`).
- Remaining lines: Target and obstacle positions (e.g., `CIBLE 3 5` or `OBSTACLE 6 8`).

Example:
```
10
10
CIBLE 3 5
CIBLE 4 9
OBSTACLE 6 8
...
```

**5. Output:**

The optimized surveillance points will be stored in a file named "res_{instance}.txt" in the "Submissions" folder. The file will contain the row and column indices of the surveillance points, separated by a space.

Example:
```
EQUIPE theo_thimote.jpeg
INSTANCE 16
2 1
5 3
...
```

**6. Results:**

The code uses integer linear programming to find the minimum number of surveillance points required to cover all targets while considering obstacles. The results may vary based on the input grid configuration.

**7. Contributing:**

Contributions to this project are welcome. If you find any issues or have suggestions for improvements, please feel free to create an issue or submit a pull request.

**8. License:**

This project is licensed under the MIT License. See the LICENSE file for more details.
