# emergencydepartment

## Installation and Running
Create a conda environment with Python==3.11.7 and install the dependencies listed in requirements.txt.

You can then run the Jupyter notebook.

## Write up
The simulation model should consider the key components of triaging, treatments, lab tests, disposition, discharge and waiting/transfer to other department.
Parameters would include: patient arrival rates, probabilties and timings for each component, timings for moving between components, and resource availabilities of each component.

There is a key assumption I made for this simplified simulation as a proof-of-concept from the patient's perspective: doctors and nurses are treated as a static resource that is 'fixed' to their component, when in reality we would consider that they are asynchronous objects that need to move to their assigned rooms and proceed with the treatment.

The simulation could also be expanded to account for complex and dynamic situations.
- different lab tests and treatments with its own probabilities, resource availabilities and timings
- different transfer and discharge protocols for different patients
- number of treatment/surgery rooms could be a separate resource from the number of doctors and nurses
- different moving times for each specific route to different rooms, and even tracking staff/patient walking speeds
- changing staffing charts across a longer time period to account for resting as well as change of shifts
- changing flow rates for different patient types, e.g. having influx of high severity patients at certain times
- considering patients that leave by themselves, or miss their queue number and need to be recalled

For future work, it would be good to have historical data on patient arrival patterns by hour as well as the occurrences and timings for each of the componentss. We would also need to know the absolute resource capacity based on doctor/nurse staffing schedules and number of beds of different departments. For my simulation, I used very arbitary numbers and kept the overall volume and capacities small to make it laptop-friendly.

It would be nice to set up Monte Carlo simulations considering normal distributions of the different parameters, and also to stress test the workflow given specific resource constraints to identify bottlenecks. The simulations could be benchmarked considering metrics such as utilization rate of resources, median and upper quartile of patient waiting times, and throughput of patients. I report the mean process and wait times for each component only.

Finally, it would be possible to optimize for distribution of resources (staff and beds). This would naturally be a multi-objective problem where we look to minimize waiting times and also minimize resource allocation (or conversely maximize resource utilization), and find the solutions along the Pareto Front. In this case the simulation is quite computationally cheap, and we could consider something like evolutionary algorithms. We can extend the simulation to different workflows as well and test for the 'best' ones.
