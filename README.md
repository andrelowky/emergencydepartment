# emergencydepartment

The simulation model should consider the key components of triaging, treatments, lab tests, disposition, discharge and waiting/transfer to other department.
Parameters would include: patient arrival rates, probabilties and timings for each component, timings for moving between each component, and resource availability of each component. We could also consider a small probability of patients leaving without treatment due to frustration.

To simulate the scenario, it would be helpful to get historical data on patient arrival patterns by day/hour as well as the median frequencies and timings for each of the key components to derive the probabilities. We would also to know the absolute resource capacity based on doctor/nurse schedules and number of beds for different departments.

With the data, we can then set up Monte Carlo simulations considering normal distributions of the different parameters, and also to stress test the workflow given specific resource constraints to identify bottlenecks. The simulations could be benchmarked considering: utilization rate of resources, median and upper quartile of patient waiting times, and throughput of patients.

The results of the simulation can allow us to optimize for distribution of resources (staff and beds), or to revamp the entire ED workflow if necessary.
