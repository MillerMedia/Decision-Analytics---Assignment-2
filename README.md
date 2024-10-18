# Project Plan Scheduling Optimization

This repository contains the code and output files for a project scheduling optimization model using Linear Programming (LP). The project focuses on determining the optimal schedule for completing a series of tasks, minimizing the total project duration (and cost). The tasks have dependencies, and this model incorporates critical path analysis to identify which tasks directly affect the project's completion time.

## Problem Overview

The project involves developing a project schedule for a group of restaurant owners in Marlborough, Massachusetts. The schedule includes 15 tasks with dependencies between them. The goal is to minimize the project's completion time and cost, assuming that all team members work at the same hourly rate and are available without resource constraints.

## Model Specification

- **Objective**: Minimize the project completion time.
- **Decision Variables**: Start times for each task.
- **Constraints**:
  - **Time Constraints**: Each task must start at or after time 0 and must finish before the project completion time.
  - **Dependency Constraints**: Each task can start only after its predecessor tasks are completed.

The linear programming model is implemented using Python's `PuLP` library, and Gantt charts are generated to visualize the task schedules and critical path.

### Scenarios

The project is analyzed under three scenarios:
- **Best-Case Scenario**: Assumes the shortest possible duration for each task.
- **Expected Scenario**: Uses the expected duration for each task.
- **Worst-Case Scenario**: Assumes the longest possible duration for each task.

### Critical Path Analysis

The critical path consists of tasks that directly affect the project's total duration. These tasks have zero slack, meaning any delay in them will delay the entire project. The critical path is identified in the output for each scenario.

## Files in the Repository

### Code
- **`project-plan.ipynb`**: Jupyter notebook containing the LP model implementation, Gantt chart generation, and critical path analysis. All code is executable in this notebook.

### Outputs
Outputs are contained in the `outputs` directory:

#### Critical path analyses
- **`output_best-case.txt`**: Critical path output for the best-case scenario.
- **`output_expected.txt`**: Critical path output for the expected scenario.
- **`output_worst-case.txt`**: Critical path output for the worst-case scenario.

#### Gantt charts
- **`gantt_best-case.png`**: Gantt chart for the best-case scenario.
- **`gantt_expected.png`**: Gantt chart for the expected scenario.
- **`gantt_worst-case.png`**: Gantt chart for the worst-case scenario.

### Excel Files
- **`data/project-plan-v003.xlsx`**: The original project plan with task dependencies and durations.

