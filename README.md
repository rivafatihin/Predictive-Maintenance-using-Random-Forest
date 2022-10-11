# Predictive-Maintenance-using-Random-Forest

# 1. Business Framing & Project overview

## Background
Manufacturing equipment is often utilized without a planned maintenance approach. Such a strategy frequently results in unplanned downtime, owing to unexpected failures. Scheduled maintenance replaces components frequently to avoid unexpected equipment stoppages, but increases the time associated with machine non-operation and maintenance cost. The emergence of Industry 4.0 and smart systems is leading to increasing attention to predictive maintenance (PdM) strategies that can decrease the cost of downtime and increase the availability (utilization rate) of manufacturing equipment. PdM also has the potential to foster sustainable practices in manufacturing by maximizing the useful lives of components.

This project is approach of Machine learning implementation (Random Forest) for Predictive Maintenance.

## Dataset source information
Dataset source from UCI link here: https://archive.ics.uci.edu/ml/datasets/AI4I+2020+Predictive+Maintenance+Dataset

## Objective
This project is try to answer below business question:
1. What is the most suitable Random Forest model that fit for Predictive Maintenance reperesent by dataset?
2. What is features/attribute the model ‘thinks’ are most important in determining failure of the machine?

# 2. Data understanding

Feature information:
*   `UDI`: unique identifier ranging from 1 to 10000.
*   `Product ID`: Product Identification number.
*   `Type`: consisting of a letter L, M, or H for low (50% of all products), medium (30%), and high (20%) as product quality variants and a variant-specific serial number.
*   `Air temperature [K]`: generated using a random walk process later normalized to a standard deviation of 2 K around 300 K.
*   `Process temperature [K]`: generated using a random walk process normalized to a standard deviation of 1 K, added to the air temperature plus 10 K.
*   `Rotational speed [rpm]`: calculated from powepower of 2860 W, overlaid with a normally distributed noise.
*   `Torque [Nm]`: torque values are normally distributed around 40 Nm with an Ïƒ = 10 Nm and no negative values.
*   `Tool wear [min]`: The quality variants H/M/L add 5/3/2 minutes of tool wear to the used tool in the process. and a 'machine failure' label that indicates, whether the machine has failed in this particular data point for any of the following failure modes are true.
*   `Target`: Categorixe condition of the Machine = Failure or Not.
*   `Failure Type`: Type of Failure, there are tool wear failure (TWF), Heat Dissipation Failure (HDF), Power Failure (PWF), Overstrain Failure (OSF), Random Failures (RNF).
