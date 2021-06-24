# Green-schedule-optimization-for-heterogeneous-computing-center
## Problem Definition
This work discuss electric energy consumption and total time used in sequencing jobs for heterogeneous computing center

![](https://github.com/EE91941387EE/Green-schedule-optimization-for-heterogeneous-computing-center/blob/main/images/%E5%9C%96%E7%89%871.png)  

Each job should be allocated to only one machine
Each job has a processing time to complete in a machine
Each machine has a given power consumption according to speed of operation to process the job in the machine

Goal: Allocate all jobs in the machines, to define their sequences on machines and to find their processing speed, minimizing the makespan and the total consumption of electricity

## Objective

minimize energy:                                               
𝑀𝑖𝑛:𝑐𝑚𝑎𝑥
 
minimize penalty:                                              
𝑀𝑖𝑛:𝑇𝐸𝐶

Decision variables:

![](https://github.com/EE91941387EE/Green-schedule-optimization-for-heterogeneous-computing-center/blob/main/images/%E5%9C%96%E7%89%872.png)  

Other setting parameter:

![](https://github.com/EE91941387EE/Green-schedule-optimization-for-heterogeneous-computing-center/blob/main/images/%E5%9C%96%E7%89%874.png)  

## Constraints

The other detailed constraints are in the paper.

https://onlinelibrary.wiley.com/doi/abs/10.1111/itor.12566

## Methodology

## 1. ϵ-constrained method

We minimize two objectives by setting one objectives to the constraint.

![](https://github.com/EE91941387EE/Green-schedule-optimization-for-heterogeneous-computing-center/blob/main/images/%E5%9C%96%E7%89%875.png)

Here are the results that minmize each objectives.

Minimize C_max : 8 min / 184 kW

![](https://github.com/EE91941387EE/Green-schedule-optimization-for-heterogeneous-computing-center/blob/main/images/%E5%9C%96%E7%89%876.png)

Minimize TEC : 15 min / 146 kW

![](https://github.com/EE91941387EE/Green-schedule-optimization-for-heterogeneous-computing-center/blob/main/images/%E5%9C%96%E7%89%877.png)

Minimize C_max

setting TEC lower than the epsilon that is the kW between 146 (min) and 184 (max).

![](https://github.com/EE91941387EE/Green-schedule-optimization-for-heterogeneous-computing-center/blob/main/images/%E5%9C%96%E7%89%878.png)

We can get the trade-off that helps the manager to decide which point is suitable for the company.

## 2. Sample Average Approximation (SAA)

We consider the parameters are not always the same number.

They have the mean and the variance and we use SAA to find the range of the objective value.

![](https://github.com/EE91941387EE/Green-schedule-optimization-for-heterogeneous-computing-center/blob/main/images/%E5%9C%96%E7%89%879.png)

![](https://github.com/EE91941387EE/Green-schedule-optimization-for-heterogeneous-computing-center/blob/main/images/%E5%9C%96%E7%89%8710.png)

## 3. marginal utility considering

More, we want to consider not only job allocating in one time but also allocating the jobs step by step.

When the machines are already assigned some jobs, we assume the speed and the power of those machine will change non-linearly.

v : speed (efficiency)

lambda : power

![](https://github.com/EE91941387EE/Green-schedule-optimization-for-heterogeneous-computing-center/blob/main/images/%E5%9C%96%E7%89%8711.png)

x-axis is the resource that machine use. It is calculated by the number of allocating jobs dividing the number of all jobs.

Step 1

![](https://github.com/EE91941387EE/Green-schedule-optimization-for-heterogeneous-computing-center/blob/main/images/%E5%9C%96%E7%89%8712.png)

Step 2

![](https://github.com/EE91941387EE/Green-schedule-optimization-for-heterogeneous-computing-center/blob/main/images/%E5%9C%96%E7%89%8713.png)

Step 3

![](https://github.com/EE91941387EE/Green-schedule-optimization-for-heterogeneous-computing-center/blob/main/images/%E5%9C%96%E7%89%8714.png)

Step 4

![](https://github.com/EE91941387EE/Green-schedule-optimization-for-heterogeneous-computing-center/blob/main/images/%E5%9C%96%E7%89%8715.png)

Step 5

![](https://github.com/EE91941387EE/Green-schedule-optimization-for-heterogeneous-computing-center/blob/main/images/%E5%9C%96%E7%89%8716.png)

From the Gantt charts, we can see the job allocating equally.

## 3. Summary

We implement a multi-objective formulation in which one of the objectives is to minimize the TEC in the scheduling while processing all the required jobs.

With ϵ-constrained method , we are capable to find the trade-off.

We use Sample Average Approximation(SAA) to find the upper bound and lower bound.

Moreover, we consider the change of marginal utility of processing rate for each machine that can allocate jobs step by step.

Reference

@article{Cota2021BicriteriaFF,
  title={Bi-criteria formulation for green scheduling with unrelated parallel machines with sequence-dependent setup times},
  author={L. P. Cota and V. N. Coelho and F. Guimar{\~a}es and Marcone J. F. Souza},
  journal={Int. Trans. Oper. Res.},
  year={2021},
  volume={28},
  pages={996-1017}
}
