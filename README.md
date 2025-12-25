# Emergency Department Simulation and Staffing Analysis

In this group final project, we develop a discrete-event simulation model of a mid-size hospital emergency department (ED) to study patient flow, congestion, and staffing efficiency.

The model captures the stochastic nature of patient arrivals, triage assignment, bed allocation, and doctor service. Through multiple simulation variants, we identify key system bottlenecks and evaluate how staffing decisions affect patient wait times, utilization, and overall performance.

## How it works

The emergency department is modeled as a two-stage process:
1. **Bed assignment**
2. **Doctor treatment**

Patients arrive randomly, are assigned a triage level (1–5), and must first secure a bed before entering the doctor queue. Beds and doctors are treated as **separate, capacity-constrained resources**, with different queueing rules depending on the model.

Key assumptions and distributions are sourced from CDC and NIH studies to reflect realistic emergency department behavior.

## Modeling Approach

### Arrival and Service Processes
- Arrivals: Poisson process (4 patients/hour)
- Triage assignment: Empirical distribution by acuity level
- Service times: Exponential distributions conditional on triage level
- Simulation horizon: 24 hours

## Simulation Models

### Model 1: Baseline FIFO Discrete-Event Simulation
- FIFO queueing for both beds and doctors
- Serves as an operational baseline
- Highlights limitations of ignoring triage priority

### Model 2: Triage Priority Monte Carlo Simulation
- Priority-based doctor queue using triage levels
- 50 Monte Carlo replications to capture variability
- Separates bed wait time and doctor wait time

### Model 3: Time-Varying Staffing Simulation
- Doctor capacity varies between day and night shifts
- Evaluates multiple staffing splits while holding total staffing constant
- Identifies optimal allocation to minimize congestion and length of stay

## Performance Metrics

System performance is evaluated using:
- Average bed waiting time
- Average doctor waiting time
- Average length of stay (LOS)
- Bed utilization rate
- Doctor utilization rate

## Tools & Technologies

- Python 3  
- NumPy  
- Matplotlib  
- Pandas (optional)  
- Discrete-event simulation & Monte Carlo methods  
- Google Colab / Jupyter Notebook
- LaTeX (for the final project report)

## Reproducibility

- Random seeds are explicitly controlled for reproducibility
- Full simulation code is included in the report appendix and Google Colab
- Each model outputs utilization metrics, wait times, LOS, and visualizations


## Notes

This project was completed as part of a final project for INDENG 174: Simulation for Enterprise-Scale Systems at UC Berkeley.

Group members: Ashlee Liu, Sukhman Sidhu, Shishira Somashekar, Viplove Rahate  
