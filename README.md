# emergencydepartment

## Installation and Running
Create a conda environment with Python==3.11.7 and install the dependencies listed in requirements.txt.

You can then run the Jupyter notebook.

## Write up
The simulation model should consider the key components of triaging, treatments, lab tests, disposition, discharge and waiting/transfer to other department.
Parameters would include: patient arrival rates, probabilties and timings for each component, timings for moving between components, and resource availabilities of each component.

To simulate the scenario, it would be helpful to get historical data on patient arrival patterns by hour as well as the occurrences and timings for each of the componentss. We would also need to know the absolute resource capacity based on doctor/nurse staffing schedules and number of beds of different departments.

With the data, we can then set up Monte Carlo simulations considering normal distributions of the different parameters, and also to stress test the workflow given specific resource constraints to identify bottlenecks. The simulations could be benchmarked considering: utilization rate of resources, median and upper quartile of patient waiting times, and throughput of patients. The results of the simulation can allow us to optimize for distribution of resources (staff and beds), or to revamp the entire ED workflow if necessary.

I made a lot of assumptions in this simplified simulation as a proof-of-concept from the patient's perspective. For example, there is only 1 moving_time parameter between all components, when in reality we would know the layout between rooms and derive the timings. Similarly, doctors and nurses are treated as a static resource that is 'fixed' to their component, when in reality we would consider that they are asynchronous objects that need to move to their assigned rooms for each new patient. 

The simulation could also be expanded to account for complex and dynamic situations.
- different lab tests and treatments with its own resource availability and timings
- number of treatment/surgery rooms could be a separate resource from the number of doctors and nurses
- probability of requiring a transfer to other departments is probably dependent on the severity of cases
- dynamic staffing charts across a longer time period to account for resting as well as change of shifts
