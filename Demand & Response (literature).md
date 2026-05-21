
Paper 1: Quantum Annealing for Residential Electric Vehicle Charging Management (QCE 2025 IEEE Conference Version)

**problem:** Determine optimal hourly binary charging/discharging schedule for residential EVs under Time-of-use pricing to minimize daily electricity cost, subject to battery capacity, load balance, and occupancy constraints. Tested at single-user and community scale (225 and 1000 households).

**Formulation**: 
Original formulation: Constrained binary optimization (effectively MIP with all-binary decision variables)
Transformation: Constrained binary problem → QUBO via penalty function method
Formulation type: QUBO
Method: Quantum Annealing on D-Wave Computer 

Paper 2: Quantum Computing-Enhanced Large-Scale Residential EV Charging Management (Applied Energy 2025 Journal Version) [Extension of paper 1]

paper 3: Assessing Quantum Computing Performance for Energy Optimization in a Prosumer Community (QAOA)

problem : Schedule binary on/off states of interruptible schedulable loads for prosumers in an energy community (day-ahead, hourly) to minimize electricity cost subject to: 
(1) maximum available power per user per hour, 
(2) each load must operate for exactly δl hours. Renewable production sharing and storage mentioned as extensions.

**Formulation:** 
Original formulation: Integer Linear Programming (ILP) / MILP
Quantum Formulation: ILP → QUBO → Ising Hamiltonian → QAOA
**Primary method:** QAOA
**Hardware:** IBM Quantum Experience — ibmq_montreal (27-qubit Falcon R4 device) + Qasm simulator (noiseless and noisy)